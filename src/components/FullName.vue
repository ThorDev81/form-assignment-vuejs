<template>
    <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
            <div class="form-group w-50 d-inline-block">
                <label for="first_name">First Name</label>
                <input
                    type="text"
                    id="first_name"
                    class="form-control"
                    v-model="first_name"
                    @input="updateName"
                />
            </div>
            <div class="form-group w-50 d-inline-block">
                <label for="last_name">Last Name</label>
                <input
                    type="text"
                    id="last_name"
                    class="form-control"
                    v-model="last_name"
                    @input="updateName"
                />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            first_name: '',
            last_name: ''
        }
    },
    methods: {
        updateName() {
            let fullName = {
                first_name: this.first_name,
                last_name: this.last_name
            };
            this.$emit('updateName', fullName);
        }
    }
}
</script>

<style scoped>

</style>