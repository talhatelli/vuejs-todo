<script setup>
import { reactive } from 'vue'

const state = reactive({
  data: 'Bu bir dinamik data',
})

const onChangeData = () => {
  state.data = 'Değiştirilen yeni bilgi'
}
</script>

<template>
  {{ state.data }}
  <hr />
  {{ test }}
  <button @click="onChangeData">Datayı değiştir</button>
  <router-link :to="{ name: 'home' }">Home</router-link>
  <router-link :to="{ name: 'about' }">About</router-link>
  <h1>Home</h1>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta nemo mollitia accusamus
    delectus, porro inventore veniam facere iste assumenda? Eligendi quis dolores ullam quas aperiam
    vel assumenda sint at delectus.
  </p>
</template>
