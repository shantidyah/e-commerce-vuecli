<template>
    <div class="modal fade" id="modal-report" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Report</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
            </button>
            </div>
            <div class="modal-body">
                <table class="table">
                    <thead>
                        <tr>
                            <th scope="col">Email</th>
                            <th scope="col">Total</th>
                            <th scope="col">Date</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for=' ( checkout, index ) in report' :key = checkout[index]>
                            <td>{{ checkout.email }}</td>
                            <td>Rp {{ checkout.total }}</td>
                            <td>{{ checkout.created_at | date }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
    name:'modalcart',
    computed:{
        ...mapState([
            'report'
        ])
    },
    filters: {
        date: function(value) {
            var gooddate = value.split('T')
            return gooddate[0]
        }
    }
}
</script>

<style>

</style>
