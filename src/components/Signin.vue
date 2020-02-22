<template>
<form>
  ID : <input type="text" name="id"><br>
  Password : <input type='text' name='password'><br>
  <input type='submit'>
</form>

</template>

<script>
export default {
  name: 'Signin',
  data () {
    return {
      msg: 'good'
    }
  }
}
</script>
