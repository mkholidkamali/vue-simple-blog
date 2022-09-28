<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add Age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const name = ref("Mario")
    const age = ref(30)

    const handleClick = () => {
      name.value = 'Luigi'
      age.value = 45
    }

    return { name, age, handleClick}
  },
  data() {
    return {
      score: 5
    }
  }
}
</script>
