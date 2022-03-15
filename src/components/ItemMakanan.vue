<template>
  <div>
    <b-card
      :title="makanan.name"
      :img-src="makanan.image"
      :img-alt="makanan.name"
      img-height="250"
      img-fluid
      img-top
      class="mb-2 object-fit-img card-item-makanan"
    >
      <b-card-text>
        Harga : Rp. {{ harga_makanan }}
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
  computed: {
    harga: function() {
      var myharga = this.makanan.price.toString().split('').reverse();
      for (var i = 0; i < myharga.length; i++) {
        if (i > 0 && i != ',' && i % 3 == 0) {
          myharga.splice(i, 0, ",");          
          myharga.join();
        }
      }
      
      return 'Rp.' + myharga.reverse().join('');
    },
    harga_makanan: function() {
      return this.formatRupiah(this.makanan.price);
    }
  },
  methods: {
    // https://www.malasngoding.com/membuat-format-rupiah-dengan-javascript/
    formatRupiah(angka, prefix) {
      var separator
      var number_string = angka.toString().replace(/[^,\d]/g, ''),
        split   		= number_string.split(','),
        sisa     		= split[0].length % 3,
        rupiah     		= split[0].substr(0, sisa),
        ribuan     		= split[0].substr(sisa).match(/\d{3}/gi);

        // tambahkan titik jika yang di input sudah menjadi angka ribuan
        if(ribuan){
          separator = sisa ? ',' : '';
          rupiah += separator + ribuan.join(',');
        }

        rupiah = split[1] != undefined ? rupiah + ',' + split[1] : rupiah;
        return prefix == undefined ? rupiah : (rupiah ? 'Rp. ' + rupiah : '');
    }
  }
};
</script>