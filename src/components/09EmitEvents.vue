<template>
  <h2>Emit Events</h2> 
  <label for="message">Mensaje</label>
  <input id="message" v-model="message" />
  <button @click="notify">Notificar al componente padre</button>
</template>

<script>
import { ref } from 'vue'
export default {
    name:'EmitEvents',
    emits: ["onFire"],
    setup(props, {emit})
    {
        const message = ref("")
        const notify =()=>{
            emit("onFire", message.value)
        }
        return { message, notify }
    }
}
</script>
