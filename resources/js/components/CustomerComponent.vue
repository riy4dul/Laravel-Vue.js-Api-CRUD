<template>
    <div id="customer">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header">Customers</div>

                    <div class="card-body">
                        <div class="table-responsive">
                            <table class="table table-hover table-bordered table-striped">
                                <thead>
                                <tr>
                                    <th scope="col">#</th>
                                    <th scope="col">Name</th>
                                    <th scope="col">Email</th>
                                    <th scope="col">Handle</th>
                                </tr>
                                </thead>
                                <tbody>
                                <tr v-for="cutomar in cutomars">
                                    <th scope="row">{{ cutomar.id }}</th>
                                    <td>{{ cutomar.name }}</td>
                                    <td>{{ cutomar.email }}</td>
                                    <td>{{ cutomar.phone }}</td>
                                </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                cutomars: "",
            }
        },

        created() {
            this.fetchCumtomar();
        },


        methods: {
            fetchCumtomar() {
                axios.get('/customersList')
                    .then(response => {
                        this.cutomars = response.data;
                        console.log(response);
                    })
                    .catch(error => {
                        console.log(error)
                    })
            }
        }
    }
</script>
