<template>
  <header class="p-3 bg-dark text-white">

    <div class="container">
      <div class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start">
        <a href="/" class="d-flex align-items-center mb-2 mb-lg-0 text-white text-decoration-none">
          <svg class="bi me-2" width="40" height="32" role="img" aria-label="Bootstrap"><use xlink:href="#bootstrap"></use></svg>
        </a>

        <form class="col-12 col-lg-auto mb-3 mb-lg-0 me-lg-3">
          <input type="search" @input="$emit('updateSearch', this.search)" v-model="search" class="form-control form-control-dark" placeholder="Rechercher un sort">
        </form>

      </div>
    </div>
  </header>
</template>

<script>
export default {
    name: "AppSearchSpell",
    emits: ["updateSearch"],
    data: function() {
        return {
            search: ""
        }
    }
};
</script>