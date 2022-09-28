<template>
  <div class="home">
    <h1>Home</h1>

    <input type="text" v-model="search">
    <p>Search Term - {{ search }}</p>

    <div v-for="name in matchingNames" :key="name">{{ name }}</div>

    <button @click="handleClick">Stop</button>
  </div>
</template>

<script>
import { ref, reactive, computed, watch, watchEffect } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'luigi'])

    const stopWatch = watch(search, () => {
      console.log('watch Func')
    }) 

    const stopEffect = watchEffect(() => {
      console.log('WatchEffect', search.value)
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }

    return { names, search, matchingNames, handleClick }
  }
}
</script>
