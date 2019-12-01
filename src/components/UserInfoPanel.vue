<template>
    <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-1 col-md-6 col-md-offset-3">
            <div class="panel panel-default">
                <div class="panel-heading">
                    <h4>Your Data</h4>
                </div>
                <div class="panel-body">
                    <p>Full Name: {{ fullName }}</p>
                    <p>Email: {{ userData.email }}</p>
                    <p>Password: {{ userData.password }}</p>
                    <p>Store in Database?: {{ storeInDatabase }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        userData: {
            first_name: String,
            last_name: String,
            email: String,
            password: String,
            store_data: Boolean
        }
    },
    computed: {
        fullName() {
            return this.userData.first_name + ' ' + this.userData.last_name;
        },
        storeInDatabase() {
            return (this.userData.store_data) ? 'Yes' : 'No';
        }
    }
}
</script>

<style scoped>

</style>