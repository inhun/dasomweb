<template>
<h1>Login my website!</h1>
<section class='message'></section>
<form action='/signin' method="post">
  ID : <input type="text" name="id"><br>
  Password : <input type='text' name='password'><br>
  <input type='submit'>
</form>
<form action="/signuppage">
    <input type="submit" name="signuppage" value="회원가입">
</form>
</template>

<script>
export default {
  name: 'App'
}
</script>
