<template>
  <q-page padding>

    <q-input color="purple-12" v-model="text1" label="item name" @keyup="log()">
    </q-input>
    <q-input color="purple-12" v-model="text1" label="item name" @keyup="log()">
    </q-input>
  </q-page>
  
</template>

<script setup>
import {ref} from "vue"
  const text1 = ref('')
  text1.value = 'Hello'

  function log() {
    console.log(text1.value)
  }
</script>
