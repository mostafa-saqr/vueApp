<template>
   <div class="topofchart pt-4 pb-4">
        <div class="container">
            <div class="row">
                <div class="col-md-12 ">
                    <h3 class="section-title text-center">Top Of The Charts</h3>
                    <div class="topofchart-carusel product-arrows owl-carousel">
                        <a class="toc-item-url" v-for="product in TopOfCharts" v-bind:href="product.hrefUrl">
                            <div class="item">
                                <div class="toc-img"><img v-bind:src="product.imageUrl" v-bind:alt="product.imageAlternateText"></div>
                                <h4> {{product.title}} </h4>
                            </div>
                        </a>
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
         TopOfCharts:{},
        }
    },
    methods:{
         topOfCharts: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/category/charts/1/1').then(response => (
          xx.TopOfCharts = response.data, 
          Vue.nextTick(function(){
            xx.installOwlCarousel()
            }.bind(xx))

          ));
        },
      installOwlCarousel : function(){
    
        $('.topofchart-carusel').owlCarousel({
        loop: true,
        margin: 10,
        nav: true,
        navText: ["<span class='icon-front-arrow'></span>", "<span class='icon-front-arrow-1'></span>"],
        responsive: {
            0: {
                items: 2,
                nav: false
            },
            480: {
                items: 2,
                nav: false
            },
            768: {
                items: 3
            },
            1000: {
                items: 4
            }
        }
    });
      }
    },
    mounted(){
        this.topOfCharts();
       
    }
   
  
}

</script>
