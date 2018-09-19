<template>
    <div>
        <top-banner></top-banner>
        <USPs></USPs>
        <middledomino></middledomino>
        <many-choices></many-choices>
        <trendingsearch></trendingsearch>
        <bottom-banner></bottom-banner>
        <cfy></cfy>
        <topofcharts></topofcharts>
    </div>
</template>
<script>
import TopBanner from './top-banner.vue';
import USPS from './USPs.vue';
import MiddleDomino from './middledomino.vue';
import ManyChoices from './many-choices.vue';
import TrendingSearch from './trendingsearch.vue';
import BottomBanner from './bottom-banner.vue';
import CFY from './cfy.vue';
import TOC from './topofcharts.vue';

export default {
    inherit: true,
    components:{
    'top-banner': TopBanner,
    'USPs': USPS,
    'middledomino': MiddleDomino,
    'many-choices': ManyChoices,
    'trendingsearch': TrendingSearch,
    'bottom-banner': BottomBanner,
    'cfy': CFY,
    'topofcharts': TOC
  },
   data () {
        return {
            
        }
    },
    methods:{
    
    },
    props: ['deviceType']
}
</script>
<style lang="scss" >
    @import '../../../assets/sass/pages/homepage';
</style>