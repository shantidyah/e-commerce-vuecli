<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light" style="background-color: #e3f2fd;">
    <a class="navbar-brand" href="#">Home</a>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto"></ul>
        <form class="form-inline my-2 my-lg-0">
          <a class="nav-link disabled" href="#" v-if='isAdmin' data-toggle="modal" data-target="#modal-add" @click="valAdd">Add</a>
          <a class="nav-link disabled" href="#" data-toggle="modal" data-target="#modal-report" v-if='isAdmin' @click="listReport">Report</a>
          <a class="nav-link disabled" href="#" v-if="!isLogin" data-toggle="modal" data-target="#modal-login">Login</a>
          <a class="nav-link disabled" href="#" data-toggle="modal" data-target="#modal-register" v-if="!isLogin">Register</a>
          <a class="nav-link disabled" href="#" style="padding-right:30px" v-else  @click="Logout">Logout</a>          
          <a href="#" v-if="!isAdmin && isLogin">
            <button id="itemCount">{{count}}</button>
            <img src="@/assets/img/cart-icon.png" width="30" height="30" class= "icon-cart" alt="" data-toggle="modal" data-target="#modal-cart">
          </a>
        </form>
      <Cart/>
      <Add/>
      <Report/>
      <Register/>
      <Login/>
    </div>
  </nav>
</template>

<script>
import {mapState, mapActions} from 'vuex'
import Cart from '@/components/ModalCart.vue'
import Add from '@/components/ModalAdd.vue'
import Report from '@/components/ModalReport.vue'
import Register from '@/components/ModalRegister.vue'
import Login from '@/components/ModalLogin.vue'

export default {
  name:'navbar',
  computed:{
    ...mapState([
      'count',
      'isLogin',
      'isAdmin'
    ])
  },
  components:{
    Cart,
    Add,
    Report,
    Register,
    Login
  },
  methods:{
    ...mapActions([
      'Logout',
      'listReport',
      'valAdd'
    ])
  }
}
</script>

<style>
#itemCount {
    position: absolute;
    display: block;
    top: 10px;
    right: 35px;    
    width: 25px;
    height: 25px;
    border-radius: 50%;
    background: red;
    color: white;
    text-align: left;
    border: none
}
</style>
