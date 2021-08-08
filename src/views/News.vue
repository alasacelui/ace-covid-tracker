<template>
    <div class="container py-5">
      <h2 class="text-center danger display-4"> News Update <img class="pb-3" src="../../public/news.svg" alt="ph" width="60"> </h2><br>
      <div class="row justify-content-center mt-4" v-if="articles.length">
          <div class="col-md-12" v-for="article in showArticle" :key="article.id">
             <div class="card w-100 p-5 mb-5 shadow p-3 mb-5 bg-white rounded rounded border-light">
                 <div class="card-body">
                    <h3 class="danger font-weight-bold card-title w-75 mx-auto text-center d-lg-block d-none">{{ article.title }}</h3>
                    <p class="danger lead font-weight-bold card-title mx-auto text-center d-lg-none"> {{ article.title }} </p>
                    
                    <br>
                 </div>
                    <img :src="article.urlToImage" v-if="article.urlToImage" ref="article_img" class="card-img-bottom loading" :title="article.title"> <br>
                    <p class="card-text lead text-center">{{ article.description }}</p>
                     <div class="card-footer text-muted text-center">
                       <span>Published at : {{ $moment(article.publishedAt).format("llll") }} </span>  <br><br>
                        <span class="">Source: <a :href="article.url">{{article.source.name}}</a> </span> 
                    </div>
             </div>
          </div>
          <nav aria-label="...">
                <ul class="pagination pagination-md justify-content-center text-center">
                    <li class="page-item"
                        :class="page === 1 ? 'disabled' : ''" >
                        
                    <a class="page-link" @click="prevPage"> Previous </a>
                    </li>
                    
                    <li class="page-link" style="background-color: inherit"> 
                    {{ page }} of {{ lastPage }}
                    </li>

                    <li class="page-item" 
                        :class="page === lastPage ? 'disabled' : ''" >
                    <a class="page-link" @click="nextPage"> Next </a>
                    </li>

                </ul>
          </nav>
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
            currentPage: 1,
            page: 1,
            perPage:20
        }
    },
    methods: {
        async getLatestNews() {
            const response = await fetch(`https://newsapi.org/v2/top-headlines?sources=fox-news,cnn,espn&pageSize=100&page=${this.currentPage}&apiKey=b2599a618b624fed83bfd3af155db3b5`)
            const {articles} = await response.json()
           
            this.articles = articles;
        },
        nextPage() {
            this.page++;
            window.scrollTo({top: 0, behavior: 'smooth'})
        },
        prevPage() {
            this.page--;
            window.scrollTo({top: 0, behavior: 'smooth'})
        },
   
    },
    computed: {
        showArticle () {
            let start = (this.page - 1) * this.perPage
            let end = start + this.perPage
            return this.articles.slice(start, end) // 0-20
        },
        lastPage () {
        let length = this.articles.length
        return Math.ceil(length / this.perPage)
        }
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