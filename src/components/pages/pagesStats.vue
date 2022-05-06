<template>
  <div class="container px-4 py-5" id="icon-grid">
    <h2 class="pb-2 border-bottom">Statistiques</h2>

    <div class="p-4 mb-3 bg-light rounded" style="margin-left: 80%;margin-right: 1%;margin-top: 1%;position: absolute;">
      <h4 class="fst-italic">Nombre de sort(s)</h4>
      <p>{{ spells.length }} sorts</p>
    </div>

    <div class="col d-flex align-items-start">
      <svg class="bi text-muted flex-shrink-0 me-3" width="1.75em" height="1.75em"><use xlink:href="#tools"></use></svg>
      <div>
        <h4 class="fw-bold mb-0">Ecoles</h4>
        <p v-for="(value, key) in frequenceEcole" :key="key">{{ key }} : {{ value }}</p>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "pagesStats",
  props: ["spells"],
  computed: {
    // Renvoie la frequence d'apparition de chaque école dans les differents sorts
    frequenceEcole() {
      let nbEcoles = {};
      this.spells.forEach(spell => {
        if (nbEcoles[spell[2]] != undefined) {
          nbEcoles[spell[2]] = nbEcoles[spell[2]] + 1;
        } else {
          nbEcoles[spell[2]] = 0;
        }
      });

      return nbEcoles;
    }
  }
};
</script>