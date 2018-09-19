<template>
    <div class="middle-domino">
        <div class="top-banner pb-4">
      
            <div class="container">
                <div class="row">
                    <div class="col-md-12">
                        <img v-bind:src="MidDomino.imageUrl" alt="" class="img-fluid">
                    </div>
                </div>
            </div>
        </div>
    <div class="latest-offer mb-4">
    <div class="container">
        <div class="row">
            <div class="col-md-4">
                <div class="card">
                    <img class="card-img-top img-fluid" src="../../../assets/images/image-14.jpg" alt="Card image cap">
                    <div class="card-body">
                        <h5 class="card-title text-center">Card title</h5>
                        <p class="card-text text-center">Lorem ipsum dolor sit amet, consectetuer adipiscing elit,</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card">
                    <img class="card-img-top" src="../../../assets/images/image-15.jpg" alt="Card image cap">
                    <div class="card-body">
                        <h5 class="card-title text-center">Card title</h5>
                        <p class="card-text text-center">Lorem ipsum dolor sit amet, consectetuer adipiscing elit,</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card">
                    <img class="card-img-top" src="../../../assets/images/image-16.jpg" alt="Card image cap">
                </div>
            </div>

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
         MidDomino:{}
        }
    },
    methods:{
        middleDomino: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/domino/middle/1').then(response => (
          xx.MidDomino = response.data[0]

          ));
        }
    },
    mounted(){
      this.middleDomino()
    }
   
}
</script>
