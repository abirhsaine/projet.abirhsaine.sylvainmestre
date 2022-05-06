<template>
        <form class="col-12 col-lg-auto mb-3 mb-lg-0 me-lg-3">
            <input type="search" @input="$emit('updateSearch', this.search)" v-model="search" class="form-control form-control-dark" placeholder="Rechercher par école">
        </form>

        <searchInfo v-for="spell in ecoleRecherches" :key="spell[2]" :spell="spell" />
</template>

<script>
import searchInfo from '../searchInfo.vue';


export default {
  name: 'pagesSpell',
  props: ["spells"],
  data: function() {
    return {
      search: ""
    };
  },
  components: {
    searchInfo,

  },
  computed: {
    // Filtre dynamique : chercher par l'école
    ecoleRecherches() {
      return this.spells.filter((spell) => spell[2].toLowerCase().includes(this.search.toLowerCase()))
    },
  }
}
</script>