<template>
  <div class="col-md-6">
    <div class="row g-0 border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative" style="margin-left: 10%;margin-top: 2%;">
      <div class="col p-4 d-flex flex-column position-static">
        <h3 class="mb-0">{{ spell[1] }}</h3>
        <div class="mb-1 text-muted">Livre : {{ spell[0] }}</div>
        <div class="mb-1 text-muted">Ecole : {{ spell[2] }}</div>
        <div class="mb-1 text-muted">Branche : <span v-for="branch in spell[3]" :key="branch">{{ branch }}</span></div>
        <div class="mb-1 text-muted">Classe : <p v-for="classes in spell[4]" :key="classes[0]">{{ classes[0] }} : {{ classes[1] }}</p></div>
        <div class="mb-1 text-muted">Durée : {{ spell[9] }}</div>
        <div class="mb-1 text-muted">Résistance à la magie : {{ spell[11] }}</div>
        <p class="card-text mb-auto"><span v-html="spell[12]"></span></p>
      </div>
      <div class="col-auto d-none d-lg-block">
        <img src="../assets/img/book.png">
      </div>
    </div>
  </div>


</template>

<script>
export default {
  name: 'searchInfo',
  props: ['spell']
}
</script>