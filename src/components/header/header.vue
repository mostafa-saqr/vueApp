<template>
    <header>
        <top-header></top-header>
        <middle-header></middle-header>
        <bottom-header></bottom-header>
    </header>
</template>

<script>
import Topheader from './top-header.vue';
import Midheader from './middle-header.vue';
import BottomHeader from './bottom-header.vue';
export default {
    components:{
    'top-header': Topheader,
    'middle-header': Midheader,
    'bottom-header': BottomHeader
  },
   data () {
        return {
            
        }
    },
    methods:{
    
    }
}
</script>
