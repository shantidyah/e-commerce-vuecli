<template>
    <div class="container">
        <div class="row">
            <div class="col-sm-3 col-md-3">
                <a href="#" @click="listCategory('sepatu')">
                    <i class="fas fa-shoe-prints fa-2x"></i>
                    SHOES
                </a>
            </div>
            <div class="col-sm-3 col-md-3">
                <a href="#" @click="listCategory('jaket')">
                    <i class="fas fa-tshirt fa-2x"></i>
                    JACKET
                </a>
            </div>
            <div class="col-sm-3 col-md-3">
                <a href="#" @click="listCategory('tas')">
                    <i class="fas fa-shopping-bag fa-2x"></i>
                    BAG
                </a>
            </div>
            <div class="col-sm-3 col-md-3">
                <a href="#" @click="listAllPro">
                    <i class="fas fa-align-justify fa-2x"></i>
                    ALL
                </a>
            </div>
        </div>
    </div>
</template>

<script>
import {mapActions} from 'vuex'

export default {
    name:'category',
    methods:{
        ...mapActions([
            'listCategory',
            'listAllPro'
        ])
    }
}
</script>

<style>
    a {
        color: black;
    }
</style>
