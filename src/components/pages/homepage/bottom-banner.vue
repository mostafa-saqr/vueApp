<template>
    <div class="bottom-banner mt-4 mb-4">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <a v-bind:href="BottomDomino.hrefUrl">
                        <img v-bind:src="BottomDomino.imageUrl" v-bind:alt="BottomDomino.alternateText" class="img-fluid"> 
                    </a>
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
         BottomDomino:{}
        }
    },
    methods:{
        bottomDomino: function(){
          var xx = this;
          axios.get('http://joi-api-catalog-service.ap-southeast-1.elasticbeanstalk.com:8081/domino/bottom/1').then(response => (
          xx.BottomDomino = response.data[0]

          ));
        }
    },
    mounted(){
      this.bottomDomino()
    }
   
}
</script>