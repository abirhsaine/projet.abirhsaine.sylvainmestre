<template>
  <pagesHeader @changePage="page => this.page = page" />

  <div class="">
    <div class="">
        <!-- onglet des sorts -->
        <pagesSpell v-if="page == 'searchSpell'" :spells="spells" />

        <!-- onglet des stats -->
        <pagesStats v-if="page === 'statistics'" :spells="spells" />
    </div>
  </div>
</template>

<script>
// Page necessaire au projet (Data, vue, CSS)
import pagesStats from './components/pages/pagesStats.vue';
import pagesHeader from './components/parts/Header.vue';
import pagesSpell from './components/pages/pagesSpell.vue';
import Data from './assets/data.min.js';
import './assets/style.css';

export default {
  name: 'App',
  data: function() {
    return {
      spells: Data, // Variable "spells" qui représente les données de data.min.js
      page: "searchSpell"
    };
  },
  components: {
    pagesHeader,
    pagesSpell,
    pagesStats
  }
}
</script>
