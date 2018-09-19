<template>
    <footer>
        <newsletter></newsletter>
        <contact></contact>
        <footer-menu></footer-menu>
        <social-links></social-links>
        <coptrights></coptrights>
    </footer>
</template>

<script>
import NewsLetter from './newsletter.vue';
import Contact from './contact.vue';
import FooterMenu from './footer-menu.vue';
import SocialLinks from './social-links.vue';
import CopyRights from './coptrights.vue';
export default {
    components:{
    'newsletter': NewsLetter,
    'contact': Contact,
    'footer-menu': FooterMenu,
    'social-links': SocialLinks,
    'coptrights': CopyRights
  },
   data () {
        return {
            
        }
    },
    methods:{
    
    }
}
</script>
