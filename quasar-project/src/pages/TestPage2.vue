
<template>
  <q-page padding>
    <q-card class="my-card bg-purple text-yellow">
      <q-card-section>
        <div v-text="naslov"></div>
        <div v-text="autor"></div>
      </q-card-section>

      <q-card-section>
        {{ lorem }}
      </q-card-section>

      <q-separator dark />

      <q-card-actions>
        <q-btn flat @click="openMsg()">Open</q-btn>
        <q-btn flat @click="deleteMsg()">Delete</q-btn>
      </q-card-actions>

      <q-card-actions>
        <q-input color="yellow" v-model="text1" label="item name" @keyup="log()"></q-input>
      </q-card-actions>
    </q-card>

    <div>
      <q-input v-model="title" label="title"></q-input>
      <q-input v-model="author" label="author"></q-input>
      <q-input v-model="text" label="text"></q-input>
      <q-btn flat @click="save()">save</q-btn>
    </div>
  </q-page>
 
</template>

<script setup>
import {ref} from "vue"
const naslov = 'Klimatske promjene'
const autor = 'Tvoja stara'
const lorem = 'bruh'

let title = ref("");
let author = ref("");
let text = ref("");

function openMsg() {
  console.log("open")
}
function deleteMsg() {
  console.log("delete")
}

function save(){
  console.log("title: "+title.value)
  console.log("author: "+author.value)
  console.log("text: "+text.value)
}

</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 500px
</style>