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
      <Carousel
        :items-to-show="1"
        :breakpoints="carouselBreakpoints"
        :wrap-around="true"
        :initial-slide="0"
        :transition="400"
        snap-align="center"
      >
        <Slide v-for="h in habilidades" :key="h.name">
          <div class="habilidad-slide d-flex flex-column align-items-center gap-2 py-3 px-2">
            <img
              :src="h.icon"
              :alt="h.name"
              class="habilidad-icon"
              width="48"
              height="48"
              loading="lazy"
            >
            <span class="small fw-semibold">{{ h.name }}</span>
          </div>
        </Slide>

        <template #addons>
          <Navigation />
          <Pagination />
        </template>
      </Carousel>
    </div>
  </section>
  <section class="home-section py-4 py-md-5">
    <h3 class="mb-4 fw-bold">Proyectos</h3>
  </section>
  <FooterComponent />

</template>

<script setup>

import NavBar from '../components/NavBar'
import FooterComponent from '../components/FooterComponent.vue'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const habilidades = [
  { name: 'HTML',              icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
  { name: 'CSS',               icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' },
  { name: 'JavaScript',        icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg' },
  { name: 'SASS',              icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg' },
  { name: 'Bootstrap',         icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original.svg' },
  { name: 'Vue',icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg' },
  { name: 'Firebase',          icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/firebase/firebase-plain.svg' },
  { name: 'GitHub',            icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg' },
  { name: 'Netlify',           icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/netlify/netlify-original.svg' },
  { name: 'Postman',           icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postman/postman-original.svg' },
]

const carouselBreakpoints = {
  768: { itemsToShow: 4, snapAlign: 'start' },
}

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

.habilidad-slide {
  width: 100%;
}

.habilidad-icon {
  width: 48px;
  height: 48px;
  object-fit: contain;
}

:deep(.carousel__prev),
:deep(.carousel__next) {
  background-color: #198754;
  border-radius: 50%;
  color: #fff;
}

:deep(.carousel__prev:hover),
:deep(.carousel__next:hover) {
  background-color: #157347;
}

:deep(.carousel__dot--active) {
  background-color: #198754;
}
</style>