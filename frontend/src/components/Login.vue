<template>
  <div class="col-sm-4 col-sm-offset-4">
    <h2>Log In</h2>
    <div class="alert alert-danger" v-if="error">
      <p>{{ error }}</p>
    </div>
    <div class="form-group">
      <input
        type="text"
        class="form-control"
        placeholder="Enter your email"
        v-model="credentials.email"
      >
    </div>
    <div class="form-group">
      <input
        type="password"
        class="form-control"
        placeholder="Enter your password"
        v-model="credentials.password"
      >
    </div>
    <button class="btn btn-primary" type="submit" @click="submit()">Log In</button>
  </div>
</template>

<script>
import auth from '../auth'

export default {

  data() {
    return {
      credentials: {
        email: '',
        password: ''
      },
      error: ''
    }
  },

  methods: {
    submit() {
      var credentials = {
        email: this.credentials.email,
        password: this.credentials.password
      }

      auth.login(this, credentials, 'home')
    }
  }

}
</script>
