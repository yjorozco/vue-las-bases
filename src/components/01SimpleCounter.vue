<template>
  <h2>Simple Counter</h2>
  <h3>{{ counter }}</h3>
  <button @click="increment">Incrementar</button>
  <button @click="decrement">Decrementar</button>
</template>

<script>
import { ref, computed } from "vue"

export default {
    name:'SimpleCounter',
    setup(){
        const counter = ref(0)
        const counterComputed = computed(
            ()=>{
                return   `El valor de counter es ${counter.value} `

            }
        )
        const increment = () => {
            counter.value++
        }

        const decrement = ()  =>{
            counter.value--
        }

        return {counter, counterComputed, decrement, increment}
    }

}
</script>

