<template>
 <div>
  <h1>Register</h1>

  <input
    type="email"
    name="email"
    v-model="email"
    placehoder="Email" />

  <br />

  <input
    type="password"
    name="password"
    v-model="password"
    placehoder="Password" />
    <br />
    <br />
    <button
      @click="register">
      Register
    </button>
 </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>
