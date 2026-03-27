<template>
  <NavBar />

  <section class="home-section py-4 py-md-5">
    <h3 class="mb-4 fw-bold">Sobre mí</h3>
    <div class="container sobre-mi d-flex flex-column flex-md-row align-items-center justify-content-center gap-4">
      <div class="sobre-mi-foto">
        <img src="/IMG_4018.jpg" alt="Paula">
      </div>
      <div class="sobre-mi-texto">
        <p class="mb-0">Mi nombre es Paula, Agrónoma de profesión y Desarrolladora Front End, por convicción. Soy chilena y vivo en Santiago. Me gusta el vino, los animales, la música y la tecnología...no necesariamente en ese orden.</p>
      </div>
    </div>
  </section>

  <section class="home-section py-4 py-md-5 mb-4 mb-md-5">
    <h3 class="mb-4 fw-bold">Habilidades/Conocimientos</h3>

    <div class="container">
      <div class="row row-cols-3 g-3 g-md-4 justify-content-center">
        <div v-for="h in habilidades" :key="h.name" class="col">
          <div class="d-flex flex-column align-items-center text-center gap-2 py-2">
            <img
              :src="h.icon"
              :alt="h.name"
              class="habilidad-icon"
              width="28"
              height="28"
              loading="lazy"
            >
            <span class="small fw-semibold">{{ h.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <FooterComponent />

</template>

<script setup>

import NavBar from '../components/NavBar'
import FooterComponent from '../components/FooterComponent.vue'

const habilidades = [
  { name: 'HTML', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
  { name: 'CSS', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' },
  { name: 'JavaScript', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg' },
  { name: 'Bootstrap', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original.svg' },
  { name: 'Vue/VueRouter/Vuex', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg' },
  { name: 'Firebase', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/firebase/firebase-plain.svg' },
  { name: 'GitHub', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg' },
  { name: 'Netlify', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/netlify/netlify-original.svg' },
  { name: 'Postman', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postman/postman-original.svg' },
]

</script>

<style scoped>
.home-divider {
  max-width: min(100%, 960px);
  margin-left: auto;
  margin-right: auto;
  opacity: 0.35;
}

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

.habilidad-icon {
  width: 28px;
  height: 28px;
  object-fit: contain;
}
</style>