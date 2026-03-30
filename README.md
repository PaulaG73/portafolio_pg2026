# Portafolio Personal — Paula Gajardo Schmidlin

Portafolio web personal desarrollado con Vue 3, que presenta información profesional, habilidades técnicas y proyectos realizados.

---

## Descripción

Sitio web de una sola página (SPA) con navegación suave entre secciones, diseño responsive y estética coherente basada en la paleta verde Bootstrap Success. Incluye secciones de presentación personal, carrusel de habilidades/conocimientos, grilla de proyectos y footer de contacto con links a redes sociales.

---

## Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| [Vue 3](https://vuejs.org/) | Framework principal (Composition API / `<script setup>`) |
| [Vue Router 4](https://router.vuejs.org/) | Enrutamiento SPA |
| [Vuex 4](https://vuex.vuejs.org/) | Gestión de estado |
| [Bootstrap 5](https://getbootstrap.com/) | Estilos y componentes UI |
| [vue3-carousel](https://ismail9k.github.io/vue3-carousel/) | Carrusel de habilidades |
| [Google Fonts — Playfair Display](https://fonts.google.com/specimen/Playfair+Display) | Tipografía de títulos |
| [Devicon](https://devicon.dev/) | Íconos de tecnologías |
| [Firebase](https://firebase.google.com/) | Backend en proyecto API Clima |

---

## Características

- Diseño **responsive** desde móvil pequeño hasta pantalla de laptop
- **Navegación** en la NavBar con scroll suave a cada sección
- Sección **Sobre mí** con foto circular y texto con palabras clave destacadas en verde
- **Carrusel** de habilidades/conocimientos con navegación manual e infinita
- Grilla de **proyectos** con tarjetas estilo Bootstrap Kitchen Sink (imagen, descripción, tecnologías, links a GitHub y Netlify)
- **Footer** con botón de inicio y links a WhatsApp, GitHub y LinkedIn
- Botones de "volver al inicio" en cada sección

---

## Estructura del proyecto

```
src/
├── components/
│   ├── NavBar.vue          # Barra de navegación
│   ├── FooterComponent.vue # Footer con íconos de contacto
│   └── CardComponent.vue   # Tarjeta de proyecto (Kitchen Sink)
├── views/
│   └── HomeView.vue        # Vista principal (todas las secciones)
├── router/
│   └── index.js            # Rutas de la aplicación
├── store/
│   └── index.js            # Store Vuex
├── App.vue
└── main.js
public/
└── index.html
```

---

## Instalación y uso

### Requisitos previos
- Node.js >= 14
- npm >= 6

### Instalación

```bash
npm install
```

### Servidor de desarrollo (hot-reload)

```bash
npm run serve
```

Abre [http://localhost:8080](http://localhost:8080) en tu navegador.

### Build para producción

```bash
npm run build
```

### Lint

```bash
npm run lint
```

---

## Contacto

- LinkedIn: [linkedin.com/in/paulagschvinologa](https://www.linkedin.com/in/paulagschvinologa)
- GitHub: [github.com/PaulaG73](https://github.com/PaulaG73)

---

*Desarrollado por Paula Gajardo Schmidlin, con Vue CLI · 2026*
