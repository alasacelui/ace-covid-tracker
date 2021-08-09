<template>
   <section id="main">
            <div class="jumbotron jumbotron-fluid text-white m-0 text-sm-center text-lg-left" id="main">
              <div class="container">
                  <div class="row">
                      <div class="d-flex">
                          <div class="section-1-text py-5 p-2">
                              <h1 class="display-4 text-dark font-weight-bold">Stay <span class="text-info font-weight-bold">Safe <img src="../../public/globe.svg" alt="safe_earth" width="60"> </span> <br>Stay<span class='text-info font-weight-bold'> Home </span></h1>
                              <p class="lead text-dark">The virus that causes COVID-19 can spread from person to person through droplets that are expelled into the air when an infected person coughs or sneezes.</p>
                                  <a class="btn btn-info " href="#">Read More</a>
                          </div>
                        
                          <img class="img-fluid d-none d-md-block" src="../../public/coronavirus.svg" alt="" width="400">
                      </div>
                  </div>
                </div>
            </div>
   </section>
    

  <section id="about_us">
    <div class="jumbotron jumbotron-fluid text-white m-0" id="section_1">
        <h1 class="text-center font-weight-bold danger">Latest Update <i class="fas fa-bell"></i></h1>
      <div class="container py-5">
        <div class="row mt-2">
          <div class="col-md-4">
            <div class="card p-4 shadow p-3 mb-5 bg-white rounded rounded">
              <div class="card-content">
                <div class="card-body">
                  <div class="media d-flex">
                      <div class="media-body text-left">
                        <h1 v-if="data.confirmed" class="danger text-dark font-weight-bold"  ref="confirmed">{{data.confirmed }}</h1>
                        <h1 v-else class="danger">Loading ...</h1>
                        <span class="text-dark">Total Confirmed Cases <img src="../../public/philippines.png" alt="ph" width="20"></span>
                      </div>
                  <div class="align-self-center">
                      <img class="float-right danger img-fluid" src="../../public/icons/patient.svg" width="50"/>
                  </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4">
              <div class="card p-4 shadow p-3 mb-5 bg-white rounded rounded">
                <div class="card-content">
                  <div class="card-body">
                    <div class="media d-flex">
                        <div class="media-body text-left">
                          <h1 v-if="data.recovered || data.recovered == 0" class="danger text-dark font-weight-bold"  ref="recovered">{{data.recovered }}</h1>
                          <h1 v-else class="danger">Loading ...</h1>

                          <span class="text-dark">Total Recovered <img src="../../public/philippines.png" alt="ph" width="20"> </span>
                        </div>
                    <div class="align-self-center">
                        <img class="float-right danger img-fluid" src="../../public/icons/recovered.svg" width="50"/>
                    </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-md-4">
                <div class="card p-4 shadow p-3 mb-5 bg-white rounded rounded">
                  <div class="card-content">
                    <div class="card-body">
                      <div class="media d-flex">
                          <div class="media-body text-left">
                            <h1 v-if="data.deaths" class="danger text-dark font-weight-bold"  ref="deaths">{{data.deaths }}</h1>
                            <h1 v-else class="danger">Loading ...</h1>
                            <span class="text-dark">Total Death <img src="../../public/philippines.png" alt="ph" width="20"></span>
                          </div>
                      <div class="align-self-center">
                        <img class="float-right danger img-fluid" src="../../public/icons/death.svg" width="50"/>
                      </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
          </div>
        </div>
    </div>
  </section>
  <section>
     <div class="jumbotron jumbotron-fluid text-white m-0" id="section_2">
        <div class="container">
            <div class="row justify-content-center">
                    <div id="carouselExampleInterval" class="carousel slide" data-ride="carousel" style="padding: 15px">
                        <div class="carousel-inner">
                          <!--First Item-->
                          <div class="carousel-item active " data-interval="10000">
                            <div class="row">
                              <div class="col-md-6">
                                    <h1 class="danger font-weight-bold">What is Corona Virus ?</h1>
                                    <br>
                                    <br>
                                   <img class="img-fluid d-none d-md-block ml-3" src="../../public/virus6.png" alt="ncov" width="350">
                              </div>

                              <div class="col-md-6 mb-4">
                                  <p class="lead">
                                  <span class="font-weight-bold danger">COVID-19</span> affects different people in different ways. Most infected people will develop mild to moderate illness and recover without hospitalization.
                                 </p>
                                  <p class="lead"><i class="fas fa-check-circle"></i>
                                  Unlike the flu, a lot of people aren’t immune to the coronavirus because it’s so new. If you do catch it, the virus triggers your body to make things called antibodies. Researchers are looking at whether they give you protection against catching it again.
                                  </p>
                                  <p class="lead"><i class="fas fa-check-circle"></i>
                                  The coronavirus also appears to cause higher rates of severe illness and death than the flu. But the symptoms themselves can vary widely from person to person.
                                  </p>
                                  <p class="lead"><i class="fas fa-check-circle"></i>
                                  Some children and teens who are in the hospital with COVID-19 have an inflammatory condition that doctors are calling multisystem inflammatory syndrome in children.
                                  </p>
                                  <button class="btn btn-lg btn-info mb-5">Read More</button>
                                
                              </div>
                            </div>
                          </div>

                          <!--Second Item-->
                          <div class="carousel-item  " data-interval="10000">
                            <div class="row">
                              <div class="col-md-6">
                                    <h1 class="danger font-weight-bold">Covid-19 Symptoms</h1>
                                    <br>
                                    <br>
                                   <img class="img-fluid d-none d-md-block ml-5" src="../../public/corona-symptoms-img.svg" alt="ncov" width="150">
                              </div>
                              
                              <div class="col-md-6">
                                  <p class="lead">
                                  <span class="font-weight-bold danger">Coronavirus</span> is an infectious disease caused by a newly discovered coronavirus.
                                  Most people who fall sick with COVID-19 will experience mild to moderate symptoms and recover without special treatment.
                                 </p>
                                 <br>
                                 <!--Symtom1-->
                                 <div class="row">
                                   <div class="col-md-2">
                                    <img class="rounded-circle" src="../../public/icons/fever.png" width="45">
                                
                                   </div>
                                   <div class="col-md-8">
                                    <h4 class="danger">High Fever</h4>
                                    <p class="lead">
                                        Even if you have mild symptoms like a headache and runny nose, stay in until you’re better.
                                    </p>
                                   </div>
                                   <div class="col-md-2"></div>
                                 </div>

                                 <!--Symtom2-->
                                 <div class="row">
                                   <div class="col-md-2">
                                    <img class="rounded-circle" src="../../public/icons/cough.png" width="45">
                                
                                   </div>
                                   <div class="col-md-8">
                                    <h4 class="danger">Coughing and Sneezing</h4>
                                    <p class="lead">
                                        Dry cough is a COVID-19 symptom that can cause pain, and cough.
                                    </p>
                                   </div>
                                   <div class="col-md-2"></div>
                                 </div>

                                  <!--Symtom3-->
                                 <div class="row">
                                   <div class="col-md-2">
                                    <img class="rounded-circle" src="../../public/icons/breath.png" width="45">
                                
                                   </div>
                                   <div class="col-md-8">
                                    <h4 class="danger">Shortness of Breath</h4>
                                    <p class="lead">
                                       Chest pain may indicate that a clot is causing a blockage or other serious danger in your arteries.
                                    </p>
                                   </div>
                                   <div class="col-md-2"></div>
                                 </div>
                              </div>
                            </div>
                          </div>

                           <!--Third Item-->
                          <div class="carousel-item " data-interval="10000">
                            <div class="row">
                              <div class="col-md-6">
                                    <h1 class="danger font-weight-bold">Covid-19 Prevention</h1>
                                    <br>
                                    <br>
                                   <img class="img-fluid d-none d-md-block ml-3" src="../../public/shield.svg" alt="ncov" width="300">
                              </div>
                              
                              <div class="col-md-6 mb-2">
                                  <p class="lead">
                                  <span class="font-weight-bold danger">Protect</span> yourself and others around you by knowing the facts and taking appropriate precautions. Follow advice provided by your local health authority..
                                 </p>
                                 <br>
                                 <!--Symptom1-->
                                 <div class="row">
                                    <div class="prevent_item_container d-flex p-3">
                                        <div class="rounded-circle prevention_img_bg">
                                            <img class="rounded-circle prevent_img" src="../../public/icons/washing-hands.png">
                                        </div>
                                        <div class="ml-3">
                                          Clean your hands often. Use soap and water, or an alcohol-based hand rub.
                                        </div>
                                    </div>
                                 </div>

                                  <!--Symptom2-->
                                 <div class="row">
                                    <div class="prevent_item_container d-flex p-3">
                                        <div class="rounded-circle prevention_img_bg">
                                            <img class="rounded-circle prevent_img" src="../../public/icons/mask.png" >
                                        </div>
                                        <div class="ml-3">
                                         Wear a mask when physical distancing is not possible.
                                        </div>
                                    </div>
                                 </div>

                                  <!--Symptom3-->
                                 <div class="row">
                                    <div class="prevent_item_container d-flex p-3">
                                        <div class="rounded-circle prevention_img_bg">
                                            <img class="rounded-circle prevent_img" src="../../public/icons/cough-cover.png" >
                                        </div>
                                        <div class="ml-3">
                                         Cover your mouth and nose with a tissue when you cough or sneeze.
                                        </div>
                                    </div>
                                 </div>

                                   <!--Symptom3-->
                                 <div class="row">
                                    <div class="prevent_item_container d-flex p-3">
                                        <div class="rounded-circle prevention_img_bg">
                                            <img class="rounded-circle prevent_img" src="../../public/icons/distancing.png" >
                                        </div>
                                        <div class="ml-3">
                                         Physical distancing refers to slow down the spread of a contagious disease.
                                        </div>
                                    </div>
                                 </div>



                              </div>
                            </div>
                          </div>
                        
                        </div>
                        <a class="carousel-control-prev" href="#carouselExampleInterval" role="button" data-slide="prev">
                          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                          <span class="sr-only">Previous</span>
                        </a>
                        <a class="carousel-control-next" href="#carouselExampleInterval" role="button" data-slide="next">
                          <span class="carousel-control-next-icon" aria-hidden="true"></span>
                          <span class="sr-only">Next</span>
                        </a>
                    </div>
            </div>
        </div>
      </div>
  </section>
  <Footer/>
</template>

<script>
import Footer from '../components/Footer.vue'
import Load from '../assets/functions'

export default {
  name:'Home',
  components:{Footer},
  data() {
    return {
      data: [],
    }
  },
  methods: {
   async getCovidSummary() {

        const res = await fetch('https://pomber.github.io/covid19/timeseries.json')
        const {Philippines} = await res.json()

          
        this.data = Philippines.pop()

  
    },
        
  },
  async mounted() {
    await this.getCovidSummary();
    Load(this.data, this.$refs.confirmed, this.$refs.recovered, this.$refs.deaths)

  },
}
</script>