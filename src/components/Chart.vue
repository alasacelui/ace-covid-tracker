<template>
 <div class="row justify-content-center py-5">
         <div class="col-12 col-md-12 col-xxl-6 d-flex order-3 order-xxl-2">
            <div class="card flex-fill w-100">
                <div class="card-body py-3">
                    <div class="chart chart-sm">
                        <canvas ref="myChart"></canvas>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'Chart',
    props: ['top_ten_countries'],
    methods:{
           displayChart() {

                const chart_ms = new Chart(this.$refs.myChart,{
                type:'line', // bar , horizontal, line ,doughnut ,radar , polarArea
                data:{
                    labels:[
                        this.top_ten_countries[0].country.name,
                        this.top_ten_countries[1].country.name,
                        this.top_ten_countries[2].country.name,
                        this.top_ten_countries[3].country.name,
                        this.top_ten_countries[4].country.name,
                        this.top_ten_countries[5].country.name,
                        this.top_ten_countries[6].country.name,
                        this.top_ten_countries[7].country.name,
                        this.top_ten_countries[8].country.name,
                        this.top_ten_countries[9].country.name,
                        ],
                    datasets:[{
                        label:`Top 10 Highest Covid Cases by Country 🌎`,
                        data: [
                        this.top_ten_countries[0].country.cases,
                        this.top_ten_countries[1].country.cases,
                        this.top_ten_countries[2].country.cases,
                        this.top_ten_countries[3].country.cases,
                        this.top_ten_countries[4].country.cases,
                        this.top_ten_countries[5].country.cases,
                        this.top_ten_countries[6].country.cases,
                        this.top_ten_countries[7].country.cases,
                        this.top_ten_countries[8].country.cases,
                        this.top_ten_countries[9].country.cases,
                        ],
                        backgroundColor:[
                        'rgba(52, 152, 219,1.0)',
                        'rgba(155, 89, 182,1.0)',
                        'rgba(52, 73, 94,1.0)',
                        'rgba(230, 126, 34,1.0)',
                        'rgba(241, 196, 15,1.0)'
                    ]
                    }],
                    
                },
                options:{
                    title: {
                        display: true,
                        text: `Top 10 Highest Covid Cases by Country  `
                    },
                    animations: {
                        tension: {
                            duration: 4000,
                            easing: 'linear',
                            from: 1,
                            to: 0,
                            loop: true
                        }
                    }
                }
            });
  
        }
    },
    mounted() {

          this.displayChart()
   

    }
}
</script>

<style>

</style>