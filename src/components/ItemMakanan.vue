<template>
  <div>
    <b-card
      :title="makanan.name"
      :img-src="makanan.image"
      :img-alt="makanan.name"
      img-height="250"
      img-fluid
      img-top
      tag="makanan"
      class="mb-2 object-fit-img card-item-makanan"
    >
      <b-card-text>
        Harga : Rp. {{ makanan.price }}
      </b-card-text>
      
      <router-link
        to="/pesan"
        class="btn btn-success btn--primary"
      >
        <b-icon-cart class="mr-2"></b-icon-cart>Pesan
      </router-link>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "ItemMakanan",
  props: ["makanan"],
};
</script>