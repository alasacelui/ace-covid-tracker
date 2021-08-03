<template>
  <div class="container py-5">
      <h2 class="text-center text-info">Track Covid-19 <i class="fas fa-globe-asia"></i> </h2>
      <div class="row justify-content-center mt-4">
          <div class="col-12">
              <br>
              <div class="form-group">
                <label>Select Country *</label>
                <select class="form-control" ref="country" v-if="countries.length" @change="getCountryCases" v-model="selected">
                    <option :value="country" v-for="(country, index) in countries" :key="index">{{ country }}</option>
                </select>
              </div>
          </div>
      </div>

       <div class="row justify-content-center mt-4">
           <div class="col-md-4">
                <div class="card p-3">
                    <div class="card-content">
                    <div class="card-body">
                        <div class="media d-flex">
                            <div class="media-body text-left">
                            <h1 class="danger text-dark"  ref="confirmed">{{ country_data.confirmed }}</h1>
                            <span class="text-dark">Total Confirmed Cases <img :src="country_code" width="20"></span>
                            </div>
                        <div class="align-self-center">
                            <img class="float-right danger" src="https://img.icons8.com/color/48/000000/protection-mask.png" width="50"/>
                        </div>
                        </div>
                    </div>
                    </div>
                </div>
           </div>
            <div class="col-md-4">
                <div class="card p-3">
                    <div class="card-content">
                    <div class="card-body">
                        <div class="media d-flex">
                            <div class="media-body text-left">
                            <h1 class="danger text-dark"  ref="recovered">{{ country_data.recovered }}</h1>
                            <span class="text-dark">Total Recovered <img :src="country_code" width="20"></span>
                            </div>
                        <div class="align-self-center">
                            <img class="float-right danger" src="https://img.icons8.com/color/48/000000/organ-transplantation.png" width="50"/>
                        </div>
                        </div>
                    </div>
                    </div>
                </div>
           </div>
           <div class="col-md-4">
                <div class="card p-3">
                    <div class="card-content">
                    <div class="card-body">
                        <div class="media d-flex">
                            <div class="media-body text-left">
                            <h1 class="danger text-dark"  ref="deaths">{{ country_data.deaths }}</h1>
                            <span class="text-dark">Total Deaths <img :src="country_code" width="20"></span>
                            </div>
                        <div class="align-self-center">
                            <img class="float-right danger" src="https://img.icons8.com/fluency/48/000000/obituary.png" width="50"/>
                        </div>
                        </div>
                    </div>
                    </div>
                </div>
           </div>
       </div>

       <Chart :top_ten_countries="top_ten_countries" v-if="top_ten_countries.length"> </Chart>

      
  </div>
</template>

<script>
import Load from '../assets/functions'
import Chart from '../components/Chart.vue'

export default {
    components: {Chart},
    data() {
        return {
            countries: [],
            countries_w_data: [],
            selected: null,
            country_data: [],
            country_code: null,
            top_ten_countries: []
        }
    },
    methods: {
       async getReports() {
            const res = await fetch('https://pomber.github.io/covid19/timeseries.json')
            const data = await res.json()
            this.countries_w_data = data;
            this.countries = Object.keys(data);

            this.getTopTenCountries()
            
        },
         getCountryCases() {
           const countries = JSON.parse(JSON.stringify(this.countries_w_data))
           this.country_data = countries[this.selected].pop()

            Load( this.country_data,this.$refs.confirmed, this.$refs.recovered, this.$refs.deaths)

            this.getCountryCode(this.selected) // get country code
            
        },
       async getCountryCode(country) {
            const res = await fetch('https://flagcdn.com/en/codes.json')
            const data = await res.json()

           
            const my_country_code = Object.keys(data).find(key => data[key] === country)
            this.country_code = `https://www.countryflags.io/${my_country_code}/flat/64.png`;
        },
        getTopTenCountries() {

            const topten =JSON.parse(JSON.stringify(this.countries_w_data)) // get all the countries with data

            const a = Object.entries(topten) // convert the object into array and loop through
            
            let c_w_key_val = []; // country with key val container
            
            const b = a.forEach(data => { // loop country (Array)
                c_w_key_val.push({
                    country: {
                        name: data[0],
                        cases : data[1].pop().confirmed
                    }
                }) // push each value to the country container []
            })

            const highest_to_lowest = c_w_key_val.sort((a,b) => { // sort from highest to lowest
                return b.country.cases - a.country.cases
            })

            const get_to_ten_highest_cases = highest_to_lowest.slice(0,10) // get the top 10

            this.top_ten_countries = get_to_ten_highest_cases
           
           
           
       }
    },
    mounted() {
        this.getReports()
    }
}
</script>

<style>

</style>
