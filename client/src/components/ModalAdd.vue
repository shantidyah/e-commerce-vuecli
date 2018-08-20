<template>
    <div class="modal fade" id="modal-add" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Add</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            </div>
            <div class="modal-body">
                type product:
                <input type="text" class="form-control" id="type" name="name" v-model="type">
                brand:
                <input type="text" class="form-control" id="brand" name="brand" v-model="brand">
                price:
                <input type="number" class="form-control" id="price" name="price" v-model="price"> {{statusPrice}} <br>
                category:
                <input type="text" class="form-control" id="category" name="category" v-model="category">
                discount:
                <input type="number" class="form-control" name="disc" v-model="discount"> {{status}} <br>
                <!-- <p style="color-red" v-if="discount>=100">discount tidak boleh lebih dari 100</p> -->
                upload image :
                <input type="file" v-on:change="selectedImage">
            </div>
            <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary" @click="addProduct">Add</button>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import {mapState,mapActions} from 'vuex'

export default {
    name:'add',
    computed:{
        ...mapState([
            'discount',
            'price',
            'type'
        ]),
        type:{
            get(){
                return this.$store.state.type
            },
            set(value){
                return this.$store.commit('type',value)
            }
        },
        brand:{
            get(){
                return this.$store.state.brand
            },
            set(value){
                return this.$store.commit('brand',value)
            }
        },
        category:{
            get(){
                return this.$store.state.category
            },
            set(value){
                return this.$store.commit('category',value)
            }
        },
        discount:{
            get(){
                return this.$store.state.discount
            },
            set(value){
                return this.$store.commit('disc',value)
            }
        },
        price:{
            get(){
                return this.$store.state.price
            },
            set(value){
                return this.$store.commit('price',value)
            }
        }

    },
    data(){
        return{
            error:'',
            status:'',
            statusPrice:''
        }
    },
    methods:{
        ...mapActions([
            'selectedImage',
            'addProduct'
        ])
    },
    watch: {
        discount: function(val) {
            if(val>100 || val<0){
                this.status = 'range discount 0-100'
            }
            else{
                this.status = ''
            }
        },
        price: function( val ) {
            if(val<=10000){
                this.statusPrice = 'price > 10000'
            }
            else{
                this.statusPrice = ''
            }
        }
    }
}
</script>

<style>

</style>
