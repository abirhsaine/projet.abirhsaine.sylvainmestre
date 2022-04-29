<template>
  <!-- Dynamiser barre de recherche -->
  <AppSearchSpell @updateSearch="search => this.search = search" />

  <div class="p-4 mb-3 bg-light rounded" style="margin-left: 80%;margin-right: 1%;margin-top: 1%;position: absolute;">
    <h4 class="fst-italic">Nombre de sort(s)</h4>
    <p>{{ sortRecherches.length }} sorts</p>
  </div>

  <!-- Boucle de l'ensemble des noms des sorts  -->
  <searchInfo v-for="spell in sortRecherches" :key="spell[1]" :spell="spell" />
</template>

<script>
import searchInfo from '../searchInfo.vue';
import AppSearchSpell from '../searchSpell.vue';

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
    AppSearchSpell,
  },
  computed: {
    // Filtre dynamique sur le nom des sorts
    sortRecherches() {
      return this.spells.filter((spell) => spell[1].toLowerCase().includes(this.search.toLowerCase()))
    }
  }
}
</script>
