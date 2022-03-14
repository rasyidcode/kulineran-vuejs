<template>
  <footer class="mt-5 mb-3">
      <hr />
      <div class="container">
          <div class="row">
              <div class="col text-center">
                  &copy; {{ current_year }} Copyright AlRasyidStudio
              </div>
          </div>
      </div>
  </footer>
</template>

<script>
export default {
    name: 'Footer',
    computed: {
        current_year: function() {
            return new Date().getFullYear()
        }
    }
}
</script>