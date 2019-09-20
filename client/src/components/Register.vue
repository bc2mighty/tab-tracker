<template>
  <div>
    <h1>Register</h1>
    <input
      name="email"
      type="email"
      v-model="email"
      placeholder="Enter Your Email"
    />
    <input
      name="password"
      type="password"
      v-model="password"
      placeholder="Enter Your Password"
    />
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  name: 'Register',
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  },
  watch: {
    email (value) {
      console.log('Email has changed to: ' + value)
    }
  },
  mounted () {
    setTimeout(() => {
      this.email = 'akinadetunmise8@gmail.com'
    }, 2000)
  }
}
</script>

<style scoped>
</style>
