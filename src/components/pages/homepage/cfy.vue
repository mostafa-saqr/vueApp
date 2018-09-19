<template>
    <div class="cfy  text-center">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <h3 class="section-title">created for you</h3>
                    <div class="cfy-slider product-carusel owl-carousel product-arrows">
                        <div class="card" v-for="product in CFY">
                            <a v-bind:href="product.hrefUrl" target="_blank">
                                <img class="card-img-top" v-bind:src="product.imageUrl" v-bind:alt="product.imageAlternateText">
                                <div class="card-body">
                                    <h5 class="card-title"> {{product.title}} </h5>
                                    <h6 class="card-price"> {{product.curruncy}} {{product.productFees}} </h6>
                                </div>
                            </a>
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
         CFY:{}

        }
    },
    methods:{
         getCFY: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/product/foryou/1/1').then(response => (
          xx.CFY = response.data, 
          Vue.nextTick(function(){
            xx.installOwlCarousel()
            }.bind(xx))
          
          
          ));
        },
      installOwlCarousel : function(){
    
        $('.cfy-slider').owlCarousel({
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
        this.getCFY()
    }
   
  
}

</script>
