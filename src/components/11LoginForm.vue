<template>
  <h2>Login Form</h2>
  <label for="email">Email</label>
  <input type="email" autocomplete="off" id="email" :value="email" name="email" @input="$emit('update:email', $event.target.value)">
  <label for="password">Password</label>
  <input type="password" autocomplete="off" id="password" :value="password" name="password" @input="$emit('update:password', $event.target.value)">

</template>

<script>
export default {
    name:'LoginForm',
    props: {
        email:{
            type: String,
            defaul:''
        },
        password:{
            type:String,
            default:''
        }
    }
}
</script>
