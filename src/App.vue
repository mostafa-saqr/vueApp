<template>
  <div class="wrapper">
    <App-header v-if="deviceType == 'desktop'"></App-header>
    <mobilemenu v-else></mobilemenu>
    <a href="#my-menu" v-if="deviceType != 'desktop'">Open the menu</a>
      <div class="page-loader">
        
        <homepage :deviceType="deviceType"></homepage>
        
      </div>
    <App-footer></App-footer>
   
  </div>
</template>



<script>

import AppHeader from 'components/header/header.vue';
import mobMenu from 'components/header/mobilemenu.vue';
import HomePage from 'components/pages/homepage/homepage.vue';
import AppFooter from 'components/footer/footer.vue';



export default {
    components:{
    'App-header': AppHeader,
    'App-footer': AppFooter,
    'homepage': HomePage,
    'mobilemenu': mobMenu
  },
  name: 'app',
  data () {
    return {
      deviceType: 'desktop',
      weblang:'ar',
      info:{}
    }
  },
  methods:{
    detecMobile: function(){
      if (window.innerWidth <= 768) {
        this.deviceType = 'mobile'
    } else if(window.innerWidth <= 991){
      this.deviceType = 'tablet'
    } else{
      this.deviceType = 'desktop'
    }
    },

  },
  mounted(){
    this.detecMobile();
    
  }
}

</script>

<style lang="scss">
  @import "assets/sass/bundle";
</style>
