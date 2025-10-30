<template>
  <q-page class="q-pa-md">
    <q-card>
      <q-card-section>
        <div class="text-h5">📚 Popis svih knjiga</div>
        <div class="text-subtitle2 text-grey">
          (Dummy podaci – klasična literatura)
        </div>
      </q-card-section>

      <q-separator />

      <q-card-section>
        <q-table
          title="Knjige"
          :rows="rows"
          :columns="columns"
          row-key="id"
          flat
          bordered
          :pagination="pagination"
          virtual-scroll
        >
          <template v-slot:body-cell-slika="props">
            <q-td :props="props">
              <q-avatar square size="48px">
                <img :src="props.row.slika" alt="slika knjige" />
              </q-avatar>
            </q-td>
          </template>
        </q-table>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const columns = [
  { name: 'id', label: 'ID', align: 'left', field: 'id', sortable: true },
  { name: 'naslov', label: 'Naslov', align: 'left', field: 'naslov', sortable: true },
  { name: 'autor', label: 'Autor', align: 'left', field: 'autor', sortable: true },
  { name: 'godina', label: 'Godina', align: 'center', field: 'godina', sortable: true },
  { name: 'zanr', label: 'Žanr', align: 'left', field: 'zanr', sortable: true },
  { name: 'slika', label: 'Slika', align: 'center', field: 'slika' },
  { name: 'stanje', label: 'Dostupnost', align: 'center', field: 'stanje', sortable: true }
]

const rows = ref([
  {
    id: 1,
    naslov: 'Gospodar prstenova',
    autor: 'John Ronald Reuel Tolkien',
    godina: 1994,
    zanr: 'Fantastika',
    slika: 'https://upload.wikimedia.org/wikipedia/commons/thumb/6/63/AnneauUnique.png/250px-AnneauUnique.png',
    stanje: 'Dostupna'
  },
  {
    id: 2,
    naslov: 'Božanstvena komedija',
    autor: 'Dante Alighieri',
    godina: 1304,
    zanr: 'ep',
    slika: 'https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Alighieri_-_Divina_Commedia%2C_Nel_mille_quatro_cento_septe_et_due_nel_quarto_mese_adi_cinque_et_sei_-_2384293_id00022000_Scan00006.jpg/250px-Alighieri_-_Divina_Commedia%2C_Nel_mille_quatro_cento_septe_et_due_nel_quarto_mese_adi_cinque_et_sei_-_2384293_id00022000_Scan00006.jpg',
    stanje: 'Posuđena'
  },
  {
    id: 3,
    naslov: 'Stranac',
    autor: 'Alberta Camusja',
    godina: 1942,
    zanr: 'Roman',
    slika: 'https://www.knjigolov.hr/slike/slika11983).jpg',
    stanje: 'Dostupna'
  },
  {
    id: 4,
    naslov: 'Zločin i kazna',
    autor: 'Fjodor Dostojevski',
    godina: 1866,
    zanr: 'Roman',
    slika: 'https://www.hocuknjigu.hr/getmedia/9c4db028-f87f-4932-86e7-989ed129a69d/9789533200613.jpg',
    stanje: 'Dostupna'
  },
  {
    id: 5,
    naslov: 'Sumrak',
    autor: 'Stephenie Meyer',
    godina: 2005,
    zanr: 'Romanticna fantastika',
    slika: 'https://upload.wikimedia.org/wikipedia/en/1/1d/Twilightbook.jpg',
    stanje: 'Posuđena'
  },
  {
    id: 6,
    naslov: 'Hamlet',
    autor: 'William Shakespeare',
    godina: 1603,
    zanr: 'Drama',
    slika: 'https://www.biblos.si/uploads/images/r_900_700/9789533284378.jpg',
    stanje: 'Dostupna'
  },
  {
    id: 7,
    naslov: 'Rat i mir',
    autor: 'Lev Tolstoj',
    godina: 1869,
    zanr: 'Roman',
    slika: 'https://www.zuzi.hr/media/img/products/49489/lav-tolstoj-rat-i-mir-NrH1.webp',
    stanje: 'Dostupna'
  },
  {
    id: 8,
    naslov: 'Don Quijote',
    autor: 'Miguel de Cervantes',
    godina: 1605,
    zanr: 'Roman',
    slika: 'https://m.media-amazon.com/images/S/compressed.photo.goodreads.com/books/1678144051i/122858226.jpg',
    stanje: 'Dostupna'
  }
])

const pagination = ref({
  rowsPerPage: 4
})
</script>
