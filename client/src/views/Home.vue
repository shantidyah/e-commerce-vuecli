<template>
  <div class="home">
    <Headers/>
    <Navbar/>
    <!-- <Carausell/> -->
    <br>
    <category/>
    <br>
    <List/>
    <Footer/>
  </div>
</template>

<script>
// // @ is an alias to /src
import Navbar from '@/components/Navbar.vue'
import Headers from '@/components/Headers.vue'
import Carausell from '@/components/Carausell.vue'
import Category from '@/components/Category.vue'
import List from '@/components/List.vue'
import Footer from '@/components/Footer.vue'
import {mapActions} from 'vuex'

export default {
  name: 'home',
  components: {
    Navbar,
    Headers,
    Carausell,
    Category,
    List,
    Footer
  },
  created(){
    this.listAllPro
    this.locStorage
  },
  computed:{
    ...mapActions([
        'listAllPro',
        'locStorage'
    ])
  }
}
</script>

<style>
  .home {
    /* background: url(https://images.pexels.com/photos/242236/pexels-photo-242236.jpeg?auto=compress&cs=tinysrgb&h=350); */
    background-color:#f7f7f7
  }
</style>

