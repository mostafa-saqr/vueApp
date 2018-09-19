<template>
    <div class="trendingsearch mt-5 mb-5">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <h3 class="section-title text-center">Trending Search</h3>
                    <ul class="list-inline">
                        <li class="list-inline-item" v-for="trend in trendingData"><a v-bind:href="trend.uri">{{trend.title}} </a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
const axios = require('axios');
export default {
 
   data () {
        return {
         trendingData:{}
        }
    },
    methods:{
        trendingSearch: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/category/trend/1/1').then(response => (
          xx.trendingData = response.data

          ));
        }
    },
    mounted(){
      this.trendingSearch()
    }
   
}
</script>
