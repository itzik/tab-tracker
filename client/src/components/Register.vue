<template>
  <div class="register">
    <h1>Register Now</h1>
    <input 
      type="email" 
      name="email" 
      v-model="email"
      placeholder="email" />
    <br>

    <input 
      type="password" 
      name="password" 
      v-model="password"
      placeholder="password" />

    <br>
    <button
      @click="register"> Register </button>
  </div>
</template>

<script>
import AuthenicationService from '@/services/AuthenticationService'

export default {
  name: 'register',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenicationService.register({
        email: this.email,
        password: this.password
      })
      // eslint-disable-next-line
      console.log(response.data)
    }
  },
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
