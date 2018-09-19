<template>
        <div class="many-choices text-center">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <h3 class="section-title">So Many Choices</h3>
                    <div class="manyChoices-slider product-carusel owl-carousel">
                        <div class="card" v-for="cat in manyChoices">
                           <a v-bind:href="cat.hrefUrl" target="_blank">
                             <img class="card-img-top" v-bind:src="cat.imageUrl" v-bind:alt="cat.imageAlternateText">
                            <div class="card-body">
                                <h5 class="card-title"> {{cat.title}} </h5>
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
         manyChoices:{},
      
        }
    },
    methods:{
         getManyChoices: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/category/choices/1/1').then(response => (
          xx.manyChoices = response.data, 
          console.log(xx.manyChoices),
          Vue.nextTick(function(){
            xx.manychoicesCarousel()
            }.bind(xx))
          
          
          ));
        },
      manychoicesCarousel : function(){
    
        $('.manyChoices-slider').owlCarousel({
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
        this.getManyChoices()
    }
   
  
}

</script>
