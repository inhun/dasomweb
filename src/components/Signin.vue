<template>
<form v-on:submit.prevent="SigninUser">
ID : <input type="text" name="id" ref="id"><br>
Password : <input type='password' name='password' ref='password'><br>
<input type='submit'>
</form>

</template>

<script>
var access_token1
export default {
  name: 'Signin',
  data () {
    return {
      access_token: access_token1
    }
  },
  methods: {
    SigninUser () {
      var id = this.$refs.id.value
      var password = this.$refs.password.value
      this.$http.post('http://api.dasom.io:8000/signin',
        {
          id: Number(id),
          password: password
        },
        {
          headers: {
            'Content-Type': 'application/json'
          }
        })
        .then(res => {
          access_token1 = res.data.data.access_token
        })
       window.open('http://localhost:8080/index')
    }
  }
}
</script>
