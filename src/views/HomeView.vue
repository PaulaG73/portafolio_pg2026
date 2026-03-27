<template>
   <NavBar />

 <h1>Portafolio</h1>
 <hr>
<section>
  <h2>Sobre mí</h2>
  <div class="container sobre-mi d-flex flex-column flex-md-row align-items-center justify-content-center gap-4">
    <div class="sobre-mi-foto">
      <img src="/IMG_4018.jpg" alt="Paula">
    </div>
    <div class="sobre-mi-texto">
      <p class="mb-0">Mi nombre es Paula, Agrónoma de profesión y Desarrolladora Front End, por convicción. Soy chilena y vivo en Santiago. Me gusta el vino, los animales, la música y la tecnología...no necesariamente en ese orden.</p>
    </div>
  </div>
</section>
  <section>
    <h2>Proyectos</h2>
  </section>

  <FooterComponent />

</template>

<script setup>

import NavBar from '../components/NavBar'
import FooterComponent from '../components/FooterComponent.vue';




</script>

<style scoped>
.sobre-mi-foto {
  --foto-tam: 140px;
  flex: 0 0 auto;
  width: var(--foto-tam);
  height: var(--foto-tam);
  border-radius: 50%;
  overflow: hidden;
  margin-inline: auto;
}

@media (min-width: 768px) {
  .sobre-mi-foto {
    --foto-tam: 160px;
    margin-inline: 0;
  }
}

.sobre-mi-foto img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.sobre-mi-texto {
  flex: 0 1 auto;
  min-width: 0;
  max-width: min(100%, 40rem);
  text-align: justify;
}
</style>