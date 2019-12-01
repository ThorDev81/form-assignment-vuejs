<template>
  <div class="container">
    <h1>Simple Sign-up Form</h1>
    <hr>
    <form>
      <app-full-name @updateName="updateName"></app-full-name>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <label for="email">Email</label>
            <input
              type="text"
              id="email"
              class="form-control"
              v-model="userData.email"
            />
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input
              type="password"
              id="password"
              class="form-control"
              v-model="userData.password"
            />
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <div class="form-group">
            <label for="storeData">
              <input
                type="checkbox"
                id="storeData"
                value="true"
                v-model="userData.store_data"
              />
              Store User Info in Database?
            </label>
          </div>
        </div>
      </div>
      <hr>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
          <button
            class="btn btn-primary"
            @click.prevent="hasBeenSubmitted = true"
          >
            Submit
          </button>  
        </div>
      </div>
    </form>
    <hr>
    <div v-show="hasBeenSubmitted">
      <app-user-panel :userData="userData"></app-user-panel>
    </div>
  </div>
</template>

<script>
import UserInfoPanel from './components/UserInfoPanel';
import FullName from './components/FullName';

export default {
  components: {
    appFullName: FullName,
    appUserPanel: UserInfoPanel
  },
  data() {
    return {
      userData: {
        first_name: '',
        last_name: '',
        email: '',
        password: '',
        store_data: false
      },
      hasBeenSubmitted: false
    }
  },
  methods: {
    updateName(event) {
      //console.log(event);
      this.userData.first_name = event.first_name;
      this.userData.last_name = event.last_name;
    }
  }
}
</script>

<style>

</style>
