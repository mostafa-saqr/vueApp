<template>
    <nav id="my-menu">
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about/">About us</a>
            <ul>
                <li><a href="/about/history/">History</a></li>
                <li><a href="/about/team/">The team</a></li>
                <li><a href="/about/address/">Our address</a></li>
            </ul>
        </li>
        <li><a href="/contact/">Contact</a></li>
    </ul>
</nav>
</template>

<script>

export default {
 
   data () {
        return {
         
        }
    },
    methods:{
        runmmenu: function(){
             $("#my-menu").mmenu();
        }
    },
    mounted(){
      this.runmmenu();
    }
   
}
</script>
