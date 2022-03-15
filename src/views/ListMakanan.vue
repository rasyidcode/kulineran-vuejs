<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>Daftar <strong>Makanan</strong></h2>
        </div>
      </div>

      <div class="row">
        <div class="col">
          <b-input-group size="md" class="mt-3">
            <template #append>
              <b-input-group-text style="cursor: pointer" @click="cariMakanan()"><b-icon-search></b-icon-search></b-input-group-text>
            </template>
            <b-form-input v-model="keyword_makanan" placeholder="Cari makanan..."></b-form-input>
          </b-input-group>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-md-4 mt-4" v-for="makanan in list_makanan" :key="makanan.id">
          <ItemMakanan :makanan="makanan" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import ItemMakanan from '@/components/ItemMakanan.vue'
import axios from 'axios';

export default {
  name: 'ListMakanan',
  components: {
    Navbar,
    ItemMakanan,
  },
  data() {
    return {
      list_makanan: [],
      keyword_makanan: ''
    }
  },
  mounted() {
    axios.get('http://localhost:3000/list-makanan')
      .then((response) => this.setListMakanan(response.data))
      .catch((err) => console.log(err));
  },
  methods: {
    setListMakanan(data) {
      this.list_makanan = data;
    },
    cariMakanan() {
      axios.get('http://localhost:3000/list-makanan/?q='+this.keyword_makanan)
      .then((response) => this.setListMakanan(response.data))
      .catch((err) => console.log(err));
    }
  }
}
</script>