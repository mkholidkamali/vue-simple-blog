<template>
  <div class="home">
    <h1>Home</h1>

    <h2>Refs</h2>
    <p>{{ siswaOne.name }} - {{ siswaOne.age }}</p>
    <button @click="updateSiswa">Update</button>

    <h2>Reactive</h2>
    <p>{{ siswaTwo.name }} - {{ siswaTwo.age }} - {{ nameTwo }}</p>
    <button @click="updateSiswaTwo">Update</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const siswaOne = ref({ name: 'mario', age: 30 })
    const siswaTwo = reactive({ name: 'luigi', age: 35 })

    const nameOne = ref('mario')
    const nameTwo = reactive('luigi')

    const updateSiswa = () => {
      siswaOne.value.age = 40
    }

    const updateSiswaTwo = () => {
      siswaTwo.age = 45
      nameTwo = 'mario'
    }

    return { siswaOne, updateSiswa, siswaTwo, updateSiswaTwo, nameTwo }
  }
}
</script>
