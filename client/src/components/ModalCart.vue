<template>
    <div class="modal fade" id="modal-cart" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Cart</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            </div>
            <div class="modal-body">
            <div class="row" v-for = "( item, index ) in cart" :key=item[index]>
                <div class="col-md-6">
                        <h4><img v-bind:src="item.url"></h4>
                    </div>
                    <div class="col-md-6 align-self-center">
                        <div class="row">
                            <h4>{{item.brand}}</h4>
                        </div>
                        <div class="row" align="left">
                            <h4>{{item.type}}</h4>
                        </div>
                        <div class="row">
                            <h4>Rp {{item.harga}}</h4>
                        </div>
                        <div class="row">
                            <!-- <div class="col-md-12"> -->
                            <button @click="deleteItem(item)">-</button><h4 class="col-md-4" align="center">{{item.qty}}</h4><button @click="addItem(item)">+</button>
                            <!-- </div> -->
                        </div>

                    </div>
                </div>
                <h4 id="total">total : Rp {{total}}</h4>
            </div>
            <div class="modal-footer">
                <!-- {{total}} -->
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary" @click="Checkout" data-dismiss="modal">Checkout</button>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import {mapState,mapActions} from 'vuex'

export default {
    name:'modalcart',
    computed:{
        ...mapState([
            'cart',
            'total'
        ])
    },
    methods:{
        ...mapActions([
            'Checkout',
            'deleteItem',
            'addItem'
        ])
    }
}
</script>

<style>

</style>
