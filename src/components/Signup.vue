<template>
<form v-on:submit.prevent="SignupUser">
  id : <input type="text" name="id" placeholder="2019000000" ref='id'><br>
  password : <input type="password" name="password" placeholder="비밀번호" ref='password'><br>
  name : <input type="text" name="name" placeholder="이름" ref='name'><br>
  email : <input type="text" name="email" placeholder="test@naver.com" ref='email'><br>
  enrollYear : <input type="text" name="enrollYear" placeholder="19" ref='enrollYear'><br>
  birth : <input type="text" name='birth' placeholder="2019-01-01" ref='birth'><br>
  <input type='submit'>

</form>

</template>

<script>
export default {
  name: 'Signup',
  data () {
    return {
      msg: 'good'
    }
  },
  methods: {
    SignupUser () {
      var id = this.$refs.id.value
      var password = this.$refs.password.value
      var name = this.$refs.name.value
      var email = this.$refs.email.value
      var enrollYear = this.$refs.enrollYear.value
      var birth = this.$refs.birth.value
      this.$http.post('http://api.dasom.io:8000/signup',
        {
          id: Number(id),
          password: password,
          name: name,
          email: email,
          enrollYear: Number(enrollYear),
          birth: birth
        },
        {
          headers: {
            'Content-Type': 'application/json'
          }
        })
        .then(res => {
          alert(res.data.status)
        })
    }
  }
}
</script>
