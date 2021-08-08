<template>
    <div class="container py-5">
      <h2 class="text-center danger display-4"> News Update <img class="pb-3" src="../../public/news.svg" alt="ph" width="60"> </h2><br>
      <div class="row justify-content-center mt-4" v-if="articles.length">
          <div class="col-md-12" v-for="article in articles" :key="article.id">
             <div class="card w-100 p-5 mb-5 shadow p-3 mb-5 bg-white rounded rounded border-light">
                 <div class="card-body">
                    <h3 class="danger font-weight-bold card-title w-75 mx-auto text-center d-lg-block d-none">{{ article.title }}</h3>
                    <p class="danger lead font-weight-bold card-title mx-auto text-center d-lg-none"> {{ article.title }} </p>
                    
                    <br>
                 </div>
                    <img :src="article.image" v-if="article.image" ref="article_img" class="card-img-bottom loading" :title="article.title"> <br>
                    <p class="card-text lead text-center">{{ article.description }}</p>
                     <div class="card-footer text-muted text-center">
                       <span>Published at : {{ $moment(article.publishedAt).format("llll") }} </span>  <br><br>
                        <span class="">Source: <a :href="article.url">{{article.source.name}}</a> </span> 
                    </div>
             </div>
          </div>
          
      </div>
      <div v-else>
          <h1>Loading ...</h1>
      </div>
    </div>
</template>

<script>

export default {
    name:'News',
    data() {
        return {
            articles: [],
        }
    },
    methods: {
        async getLatestNews() {
            const response = await fetch(`https://gnews.io/api/v4/top-headlines?country=ph&q=covid&token=113db9b688ed91b692a524abb418d308`)
            const {articles} = await response.json()
           
            this.articles = articles;
            
        },

    },
    mounted() {
        this.getLatestNews();
    }

}
</script>

<style scoped>

.loading {
  background: transparent url('https://miro.medium.com/max/882/1*9EBHIOzhE1XfMYoKz1JcsQ.gif') center no-repeat;
}

</style>