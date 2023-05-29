<template>
<hello-world />
<hr />
<simple-counter />
<hr />
<reactive-counter />
<hr />
<watch-counter />
<hr />
<todo-list />
<hr />
<simple-fetch />
<hr />
<Suspense>
  <template #default>
    <suspence-fetch />
  </template>
  <template #fallback>Cargando información de la api......</template>
</Suspense>
<hr />
<profile-with-props name="luis" :age="32"/>
<hr />
<emit-events @onFire="eventEmittedFromChild"/>
<hr />
<root-events />
<hr />
<login-form 
 v-model:email="email"
 v-model:password="password"

/>
{{ email }} -{{ password }}
</template>

<script>
// @ is an alias to /src
import {reactive, toRefs} from 'vue'
import HelloWorld from '@/components/00HelloWorld.vue'
import SimpleCounter from '@/components/01SimpleCounter.vue'
import ReactiveCounter from '@/components/02ReactiveCounter.vue'
import WatchCounter from '@/components/03WatchCounter.vue'
import TodoList from '@/components/04TodoList.vue'
import SimpleFetch from '@/components/05SimpleFetch.vue'
import SuspenceFetch from '@/components/06SuspenceFetch.vue'
import ProfileWithProps from  '@/components/08ProfileWithProps.vue'
import EmitEvents from  '@/components/09EmitEvents.vue'
import RootEvents from  '@/components/10RootEvents.vue'
import LoginForm from  '@/components/11LoginForm.vue'
export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    SimpleCounter,
    ReactiveCounter,
    WatchCounter,
    TodoList,
    SimpleFetch,
    SuspenceFetch,
    ProfileWithProps,
    EmitEvents,
    RootEvents,
    LoginForm
  },
  setup(){
    const eventEmittedFromChild = (message) =>{
      console.log(message)
    }
    const login = reactive({
      email:"test",
      password:"password"
    })

    return {...toRefs(login), eventEmittedFromChild}
  }
}
</script>
