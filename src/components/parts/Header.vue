<template>
  <section>
      <div class="row">
        <div class="embed-responsive embed-responsive-16by9">
          <img src="../../assets/img/library.jpeg" style="width: 100%;height: 100%;">
        </div>
        <div class="titrevideo text-center" style="background-color: #f0c300bd;">
          <div class="borderbottom typewriter">
            <h1 style="font-weight: bold;">Bienvenue dans notre bibliothèque de sorts !</h1>
          </div>
        </div>
      </div>

  </section>

  <div class="p-3 bg-light text-white">
    <div class="container">
      <div class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start">
        <div class="placeholder">
          <a href="">

          </a>
        </div>
      </div>
    </div>

    <nav class="nav col-12 col-lg-auto me-lg-auto mb-2 justify-content-center mb-md-0">
      <img src="../../assets/img/home.png" style="width: 66px;height: 66px;" class="nav-link px-2 text-white" @click="$emit('changePage', 'searchSpell')">
      <img src="../../assets/img/config.png" style="width: 66px;height: 66px;" class="nav-link px-2 text-white" @click="$emit('changePage', 'configuration')">
      <img src="../../assets/img/stats.png" style="width: 66px;height: 66px;" class="nav-link px-2 text-white" @click="$emit('changePage', 'statistics')">
    </nav>
  </div>

</template>

<script>
export default {
  name: 'pagesHeader'
}
</script>
