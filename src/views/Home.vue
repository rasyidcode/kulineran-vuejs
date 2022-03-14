<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />

      <div class="row mt-5">
        <div class="col">
          <h2>Paling <strong>Populer</strong></h2>
        </div>
        <div class="col">
          <router-link
            to="/list-makanan"
            class="btn btn-success btn--primary float-right"
          >
            <b-icon-eye class="mr-2"></b-icon-eye>Lihat Semua
          </router-link>
        </div>
      </div>

      <div class="row mb-3 mt-4">
        <div class="col-md-4 mt-d" v-for="makanan in makanan_populer" :key="makanan.id">
          <ItemMakanan :makanan="makanan" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import ItemMakanan from "@/components/ItemMakanan.vue";
import axios from 'axios';

export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    ItemMakanan
  },
  data() {
    return {
      makanan_populer: []
    }
  },
  methods: {
    setMakananPopuler(data) {
      this.makanan_populer = data;
    }
  },
  mounted() {
    axios.get('http://localhost:3000/makanan-populer')
      .then((response) => this.setMakananPopuler(response.data))
      .catch((err) => console.log(err));
  }
};
</script>
