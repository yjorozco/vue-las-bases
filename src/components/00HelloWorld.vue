<template>
  <h2>Hola Mundo</h2>
  <p>{{message}}</p>
  <label for="message" class="for">Mensaje</label>
  <input id="message" v-model="message">
</template>

<script>
import { ref } from "vue"
export default {
  name: 'HelloWorld',
  setup(){
    const message = ref("Mensaje desde el componente helloworld")
    return { message }
  }
}
</script>

