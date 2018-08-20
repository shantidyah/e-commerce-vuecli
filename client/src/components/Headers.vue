<template>
    <header id='header'>
        <div class="container">
            <div class="row">
                <div class="col-md-4">
                    <h1 id='logo'>Let's Shop</h1>
                </div>
                <div class="col-md-8">
                    <!-- {{search}} -->
                    <form class="form-inline" id='search'>
                        <input class="form-control mr-sm-2" type="search" v-model="search" placeholder="Search" aria-label="Search" id='input-search'>
                        <button class="btn my-2 my-sm-0" type="submit" id="submit-search" @click="Search">Search</button>
                    </form>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
import {mapState,mapActions} from 'vuex'

export default {
    name:'search',
    computed:{
        ...mapState([
            'search'
        ]),
        search:{
            get(){
                return this.$store.state.search
            },
            set(value){
                return this.$store.commit('search',value)
            }
        }
    },
    methods:{
        ...mapActions([
            'Search'
        ])
    }
}
</script>

<style>
    #header {
        height: 100px;
        background: url('https://s0.bukalapak.com/images/header-lapak-default.jpg')
    }
    #logo {
        font-family: sans-serif;
        padding-top: 20px
    }
    #search {
        float: right;
        /* text-align: right; */
        margin-top: 5%;
    }
</style>
