<template>
  <div class="hero">
    <!-- Desktop -->
    <div class="d-md-block d-none">
      <div class="row mt-5">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2><strong>Menu Makanan Enak</strong> <br />di Gadgetmu!</h2>
              <p>Ayo segera pilih dan pesan makanan favorite Anda</p>
              <router-link
                to="/"
                class="btn btn-success btn--primary"
              >
                <b-icon-arrow-right class="mr-2"></b-icon-arrow-right>Pesan
              </router-link>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img
            src="../assets/images/hero.svg"
            width="100%"
            alt="Orang makan-makan"
          >
        </div>
      </div>
    </div>

    <!-- Mobile -->
    <div class="d-sm-block d-md-none">
      <div class="row mt-5 ">
        <div class="col-md-6">
          <img
            src="../assets/images/hero.svg"
            width="100%"
            alt="Orang makan-makan"
          >
        </div>
        <div class="col-md-6">
          <div class="d-flex h-100 mt-4">
            <div class="justify-content-center align-self-center text-center">
              <h2><strong>Menu Makanan Enak</strong> <br />di Gadgetmu!</h2>
              <p>Ayo segera pilih dan pesan makanan favorite Anda</p>
              <router-link
                to="/"
                class="btn btn-success btn--primary"
              >
                <b-icon-arrow-right class="mr-2"></b-icon-arrow-right>Pesan
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style>
</style>