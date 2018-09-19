<template>
    <div class="banner">
        <div class="container-fluid">
            <div class="row">
            <div class="bancontainer-loader" v-if="loading"></div>
                <div class="owl-carousel header-slider" v-if="!loading">
                    <div class="bann-container" v-for="banner in topBanners">
                        <img v-bind:src="banner.imageUrl" width="100%" v-bind:alt="banner.alternateText" class="img-fluid">
                        <div class="bann-desc">
                            <span class="bann-text d-block">{{banner.title}} </span>
                            <a v-bind:href="banner.hrefUrl" class="bann-link">{{banner.btnText}} </a>
                        </div>
                    </div>
                   
                </div>
            </div>
        </div>
    </div>
</template>
<script>
const axios = require('axios');
import Vue from 'vue'
export default {
 
   data () {
        return {
         topBanners:{},
         loading:true
        }
    },
    methods:{
        TopBanner: function(){
          var xx = this;
          axios.get('https://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/domino/top/1').then(response => (
          xx.topBanners = response.data, 
          console.log(xx.topBanners),
          this.loading = false,
          Vue.nextTick(function(){
            xx.OpenCarusel()
            }.bind(xx))
    
          ));
        },
        OpenCarusel: function(){
            $('.header-slider').owlCarousel({
                loop: true,
                margin: 10,
                nav: true,
                navText: ["<span class='icon-front-arrow'></span>", "<span class='icon-front-arrow-1'></span>"],
                dots: false,
                responsive: {
                    0: {
                        items: 1,
                        nav: false,
                        dots: true
                    },
                    480: {
                        items: 1,
                        nav: false,
                        dots: true
                    },
                    768: {
                        items: 1
                    },
                    1000: {
                        items: 1
                    }
                }
            });
      }
    },
    mounted(){
      this.TopBanner()
    }
   
}

</script>
<style> 
.bancontainer-loader {
    width: 100%;
    height: 400px;
    background-color: rgb(218, 218, 218);
    -webkit-animation-name: example; /* Safari 4.0 - 8.0 */
    -webkit-animation-duration: 0.5s; /* Safari 4.0 - 8.0 */
    -webkit-animation-iteration-count: infinite; /* Safari 4.0 - 8.0 */
    animation-name: example;
    animation-duration: 0.5s;
    animation-iteration-count: infinite;
}

/* Safari 4.0 - 8.0 */
@-webkit-keyframes example {
    from {background-color: rgb(218, 218, 218);}
    to {background-color: white;}
}

/* Standard syntax */
@keyframes example {
    from {background-color: rgb(218, 218, 218);}
    to {background-color: white;}
}
</style>