<template>
    <div style="padding-left:35px; padding-right:35px;">
        <div class="row">
            <div class="col-md-3" style="margin-bottom:20px;" v-for="( product, index ) in products" :key=product[index] >
                <div class="card">
                    <img class="card-img-top" v-bind:src="product.url" alt="Card image cap" style="width:70%; margin-left:15%;">
                    <div v-if="product.discount==0"></div>
                    <button id="disc" v-else><b>{{product.discount}}%</b></button>
                    <div class="card-body" align="left">
                        <h5>{{product.brand}}</h5>
                        <h5 v-if="product.discount>0">Rp <s>{{product.price}}</s> {{product.price - (product.price * product.discount/100)}}</h5>
                        <h5 v-else>Rp {{product.price}}</h5>
                        <h6>{{product.type}}</h6>
                        <div align="right" v-if='!isAdmin && isLogin'>
                            <button class="btn btn-light" @click="addCart({product:product,discount:product.price - (product.price * product.discount/100)})">add to cart</button>
                        </div>
                        <div align="right" v-if='isAdmin'>
                            <button class="btn btn-info" style="margin-right:10px" data-toggle="modal" data-target="#modal-edit" @click="valueEdit(product)">edit</button>
                            <button class="btn btn-danger" @click="Delete(product._id)">delete</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Edit/>
    </div>
</template>

<script>
import {mapState,mapActions} from 'vuex'
import Edit from '@/components/ModalEdit.vue'

export default {
    name:'list',
    data(){
        return{
 
        }
    },
    components : {
        Edit
    },
    computed:{
        ...mapState([
            'products',
            'isAdmin',
            'isLogin'
        ])
    },
    methods:{
        ...mapActions([
            'addCart',
            'valEdit',
            'Delete'
        ]),
        valueEdit(product){
            this.valEdit(product)
        }
    }
}
</script>

<style>
#disc {
    position: absolute;
    display: block;
    top: 20px;
    right: 35px;    
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: red;
    color: white;
    text-align: center;
    border: none
}
</style>
