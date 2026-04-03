<template>
  <div class="home-view">
    <NavBar />

    <main class="home-main">
      <section id="sobre-mi" class="home-section py-4 py-md-5">
        <h3 class="mb-4 fw-bold">Sobre mí</h3>
        <div class="container sobre-mi d-flex flex-column flex-md-row align-items-center justify-content-center gap-4">
          <div class="sobre-mi-foto">
            <img src="/IMG_4018.jpg" alt="Paula">
          </div>
          <div class="sobre-mi-texto">
            <p class="mb-2">Mi nombre es Paula, <span class="highlight">Agrónoma</span> de profesión.</p>
            <p class="mb-2"><span class="highlight"> y Desarrolladora Front End</span>, por convicción.</p>
            <p class="mb-2">Soy <span class="highlight">chilena</span> y vivo en <span class="highlight">Santiago</span>.</p>
            <p class="mb-2">Me gusta el <span class="highlight">vino</span>, los <span class="highlight">animales</span>, la <span class="highlight">música</span> y la <span class="highlight">tecnología</span>...</p>
            <p class="mb-0 frase-final"><strong>...no necesariamente en ese orden.</strong></p>
          </div>
        </div>
        <div class="container text-end mt-3">
          <a href="#" class="btn btn-sm btn-outline-success rounded-circle p-1 btn-top" title="Volver al inicio" aria-label="Volver al inicio">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
              <path d="M8 12a.5.5 0 0 0 .5-.5V5.707l2.146 2.147a.5.5 0 0 0 .708-.708l-3-3a.5.5 0 0 0-.708 0l-3 3a.5.5 0 0 0 .708.708L7.5 5.707V11.5a.5.5 0 0 0 .5.5z"/>
            </svg>
          </a>
        </div>
      </section>

      <section id="habilidades" class="home-section py-4 py-md-5">
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
        <div class="container text-end mt-3">
          <a href="#" class="btn btn-sm btn-outline-success rounded-circle p-1 btn-top" title="Volver al inicio" aria-label="Volver al inicio">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
              <path d="M8 12a.5.5 0 0 0 .5-.5V5.707l2.146 2.147a.5.5 0 0 0 .708-.708l-3-3a.5.5 0 0 0-.708 0l-3 3a.5.5 0 0 0 .708.708L7.5 5.707V11.5a.5.5 0 0 0 .5.5z"/>
            </svg>
          </a>
        </div>
      </section>
      <section id="proyectos" class="home-section py-4 py-md-5">
        <h3 class="mb-4 fw-bold">Proyectos</h3>
        <div class="container">
          <div class="row g-3 justify-content-center">
            <div v-for="proyecto in proyectos" :key="proyecto.title" class="col-10 col-sm-6 col-md-4">
              <CardComponent
                :title="proyecto.title"
                :description="proyecto.description"
                :image="proyecto.image"
                :tags="proyecto.tags"
                :github-url="proyecto.githubUrl"
                :netlify-url="proyecto.netlifyUrl"
              />
            </div>
          </div>
        </div>
        <div class="container text-end mt-3">
          <a href="#" class="btn btn-sm btn-outline-success rounded-circle p-1 btn-top" title="Volver al inicio" aria-label="Volver al inicio">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
              <path d="M8 12a.5.5 0 0 0 .5-.5V5.707l2.146 2.147a.5.5 0 0 0 .708-.708l-3-3a.5.5 0 0 0-.708 0l-3 3a.5.5 0 0 0 .708.708L7.5 5.707V11.5a.5.5 0 0 0 .5.5z"/>
            </svg>
          </a>
        </div>
      </section>
      <div id="contacto">
        <FooterComponent />
      </div>
    </main>
  </div>
</template>

<script setup>

import NavBar from '../components/NavBar'
import FooterComponent from '../components/FooterComponent.vue'
import CardComponent from '../components/CardComponent.vue'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

const habilidades = [
  { name: 'HTML',              icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
  { name: 'CSS',               icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' },
  { name: 'JavaScript',        icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg' },
  { name: 'SASS',              icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg' },
  { name: 'Bootstrap',         icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bootstrap/bootstrap-original.svg' },
  { name: 'Vue', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg' },
  { name: 'Firebase',          icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/firebase/firebase-plain.svg' },
  { name: 'GitHub',            icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg' },
  { name: 'Netlify',           icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/netlify/netlify-original.svg' },
  { name: 'Postman',           icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postman/postman-original.svg' },
]

const carouselBreakpoints = {
  480: { itemsToShow: 2, snapAlign: 'start' },
  768: { itemsToShow: 4, snapAlign: 'start' },
}

const proyectos = [
  {
    title: 'Catálogo Vinos Semana Santa',
    description: 'SPA en Vue 3 que muestra oferta de packs de vinos para Semana Santa: Presentación de marca, carrusel de tarjetas con datos desde JSON y pie de página con direccionamiento a whatsapp..',
    image: '/Vinóloga IA.jpg',
    tags: ['HTML', 'JavaScript', 'Vue', 'Bootstrap'],
    githubUrl: 'https://github.com/PaulaG73/catalogo_vinos',
    netlifyUrl: 'https://catalogovinos.netlify.app',
  },
  {
    title: 'Playas soñadas de América',
    description: 'SPA con playas de América, clima en vivo (Open-Meteo + Axios), Firebase Auth (registro, login, recuperación de contraseña) y favoritos en Cloud Firestore.',
    image: '/Florianópolis_Brasil2.jpg',
    tags: ['HTML', 'CSS', 'JavaScript','Vue', 'Bootstrap', 'Firebase'],
    githubUrl: 'https://github.com/PaulaG73/ej_portafolio_m8',
    netlifyUrl: 'https://portafoliom8.netlify.app',
  },
]

</script>

<style scoped>
/* Contenido empieza bajo la barra fija; anclas respetan la altura del nav */
.home-main {
  padding-top: 5.5rem;
}

@media (min-width: 992px) {
  .home-main {
    padding-top: 6rem;
  }
}

.home-section,
#contacto {
  scroll-margin-top: 5.5rem;
}

@media (min-width: 992px) {
  .home-section,
  #contacto {
    scroll-margin-top: 6rem;
  }
}

.home-section {
  background-color: #e4f5ec;
}

.home-divider {
  max-width: min(100%, 960px);
  margin-left: auto;
  margin-right: auto;
  opacity: 0.35;
}

.home-section h3 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1.1rem, 3.5vw, 1.5rem);
  letter-spacing: 0.02em;
  display: inline-block;
  position: relative;
  padding-bottom: 0.35rem;
}

.home-section h3::after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 0;
  transform: translateX(-50%);
  width: 60%;
  height: 3px;
  background-color: #198754;
  border-radius: 2px;
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
  line-height: 1.9;
  font-size: clamp(0.9rem, 2.5vw, 1rem);
}

.highlight {
  color: #198754;
  font-style: italic;
  font-weight: bold;
}

.frase-final {
  font-style: italic;
  animation: colorPulse 3s ease-in-out infinite;
}

@keyframes colorPulse {
  0%   { color: #2c3e50; }
  50%  { color: #198754; }
  100% { color: #2c3e50; }
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

.btn-top {
  width: 2rem;
  height: 2rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  line-height: 1;
}
</style>