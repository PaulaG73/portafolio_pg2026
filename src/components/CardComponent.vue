<template>
  <div class="card shadow-sm border-success">
    <img :src="image" class="card-img-top" :alt="title">
    <div class="card-body">
      <h5 class="card-title fw-bold">{{ title }}</h5>
      <p class="card-text">{{ description }}</p>
      <p class="card-tags mb-0">
        <template v-for="(tag, index) in tags" :key="tag">
          <span v-if="index > 0" class="tag-dot">•</span>{{ tag }}
        </template>
      </p>
    </div>
    <hr class="card-divider">
    <div class="card-body">
      <a :href="githubUrl" target="_blank" rel="noopener noreferrer" class="card-link" title="Ver en GitHub" aria-label="Ver en GitHub">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg" width="28" height="28" alt="Ver en GitHub">
      </a>
      <a :href="netlifyUrl" target="_blank" rel="noopener noreferrer" class="card-link" title="Ver en Netlify" aria-label="Ver en Netlify">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/netlify/netlify-original.svg" width="28" height="28" alt="Ver en Netlify">
      </a>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    default: '',
  },
  image: {
    type: String,
    required: true,
  },
  tags: {
    type: Array,
    default: () => [],
  },
  githubUrl: {
    type: String,
    default: '#',
  },
  netlifyUrl: {
    type: String,
    default: '#',
  },
})
</script>

<style scoped>
.card-img-top {
  height: 110px;
  object-fit: cover;
}

.card-title {
  font-family: 'Playfair Display', Georgia, serif;
}

.card-tags {
  font-size: 0.8rem;
  color: #555;
}

.card-divider {
  border-color: #198754;
  opacity: 0.5;
  margin: 0;
}

.tag-dot {
  color: #198754;
  margin: 0 0.3rem;
  font-weight: bold;
  font-size: 1rem;
}
</style>
