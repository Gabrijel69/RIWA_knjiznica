<template>
  <q-page class="flex flex-center">
    <div class="q-pa-la">
      <div class="q-gutter-lg">

        <h4>Unos novih knjiga</h4>

        <q-input style="width: 500px" outlined v-model="text" label="Naslov" />

        <q-input style="width: 500px" outlined v-model="text" label="Autor" />

        <q-input style="width: 500px" v-model="text" filled type="textarea" label="Opis Knjige"/>

        <q-file style="width: 500px" v-model="filesImages" filled accept=".jpg, image/*" multiple @rejected="onRejected" label="Unos slike"/>

        <q-select style="width: 500px" filled v-model="model" :options="options" label="Filled" />

        <q-btn style="width: 238px" color="primary" label="Spremi" />
        <q-btn style="width: 238px" color="red" label="Odustani" />
      </div>
    </div>
  </q-page>
</template>

<script>

import { ref } from 'vue'

export default {
  setup () {
    return {
      model: ref(null),
      options: [
        'Slobodna', 'Zauzeta'
      ]
    }
  }
}

</script>
