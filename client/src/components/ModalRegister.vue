<template>
    <div class="modal fade" id="modal-register" tabindex="-1" role="dialog" aria-labelledby="exampleModalLongTitle" aria-hidden="true">
        <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLongTitle">Register</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            </div>
            <div class="modal-body">
            name:
            <input type="text" class="form-control" name="name" v-model="name">
            email:
            <input type="text" class="form-control" name="email" v-model="email">
            password:
            <input type="password" class="form-control" name="password" v-model="password">
            address:
            <input type="text" class="form-control" name="address" v-model="address">
            city:
            <input type="text" class="form-control" name="city" v-model="city">
            </div>
            <!-- <h5 style='color:red'>{{warning}}</h5> -->
            <div class="modal-footer">
            <button type="button" class="btn btn-primary" @click="register" data-dismiss="modal">Save</button>
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
import {mapState,mapActions} from 'vuex'

export default {
    name:'register',
    computed:{
        ...mapState([
            'name',
            'email',
            'password',
            'address',
            'city'
        ]),
        name:{
            get(){
                return this.$store.state.name
            },
            set(value){
                return this.$store.commit('name',value)
            }
        },
        email:{
            get(){
                return this.$store.state.email
            },
            set(value){
                return this.$store.commit('email',value)
            }
        },
        password:{
            get(){
                return this.$store.state.password
            },
            set(value){
                return this.$store.commit('password',value)
            }
        },
        address:{
            get(){
                return this.$store.state.address
            },
            set(value){
                return this.$store.commit('address',value)
            }
        },
        city:{
            get(){
                return this.$store.state.city
            },
            set(value){
                return this.$store.commit('city',value)
            }
        }
    },
    methods:{
        ...mapActions([
            'register'
        ])
    }
}
</script>

<style>

</style>
