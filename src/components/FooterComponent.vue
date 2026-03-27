<template>
  <footer class="footer py-4 mt-auto d-flex flex-column align-items-center gap-3">
    <p class="mb-0">Derechos reservados &copy; 2026 Paula Gajardo Schmidlin</p>
    <div class="d-flex align-items-center justify-content-center gap-4">
      <a
        class="btn btn-success rounded-circle p-2 footer-action-btn shadow-sm"
        :href="whatsappUrl"
        target="_blank"
        rel="noopener noreferrer"
        :aria-disabled="!whatsappReady"
        :class="{ 'opacity-50': !whatsappReady }"
        :title="whatsappReady ? 'Contactar por WhatsApp' : 'Configura WHATSAPP_NUMBER_DIGITS en FooterComponent.vue'"
        aria-label="Abrir chat de WhatsApp"
      >
        <svg
          class="footer-action-icon"
          xmlns="http://www.w3.org/2000/svg"
          width="28"
          height="28"
          fill="currentColor"
          viewBox="0 0 24 24"
          aria-hidden="true"
        >
          <path
            d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.435 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"
          />
        </svg>
      </a>
      <button
        type="button"
        class="btn btn-dark rounded-circle p-2 footer-action-btn shadow-sm"
        aria-label="Volver al inicio"
        title="Volver al inicio"
        @click="irAlInicio"
      >
        <svg
          class="footer-action-icon"
          xmlns="http://www.w3.org/2000/svg"
          width="28"
          height="28"
          fill="currentColor"
          viewBox="0 0 16 16"
          aria-hidden="true"
        >
          <path
            d="M8.354 1.146a.5.5 0 0 0-.708 0l-6 6A.5.5 0 0 0 1.5 7.5v7a.5.5 0 0 0 .5.5h4.5a.5.5 0 0 0 .5-.5v-4h2v4a.5.5 0 0 0 .5.5H14a.5.5 0 0 0 .5-.5v-7a.5.5 0 0 0-.146-.354L13 5.793V2.5a.5.5 0 0 0-.5-.5h-1a.5.5 0 0 0-.5.5v1.293L8.354 1.146zM2.5 14V7.707l5.5-5.5 5.5 5.5V14H10v-4a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0-.5.5v4H2.5z"
          />
        </svg>
      </button>
    </div>
  </footer>
</template>

<script setup>
import { computed, nextTick } from 'vue'
import { useRouter } from 'vue-router'

// ========== RELLENA AQUÍ ==========
/** Solo dígitos: código de país + número (sin + ni espacios). Ej. Chile: 56912345678 */
const WHATSAPP_NUMBER_DIGITS = '56996450950'
// ===================================

const whatsappReady = computed(() => WHATSAPP_NUMBER_DIGITS.replace(/\D/g, '').length > 0)

const whatsappUrl = computed(() => {
  const digits = WHATSAPP_NUMBER_DIGITS.replace(/\D/g, '')
  if (!digits) return '#'
  return `https://wa.me/${digits}`
})

const router = useRouter()

async function irAlInicio() {
  if (router.currentRoute.value.name !== 'home') {
    await router.push({ name: 'home' })
    await nextTick()
  }
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<style scoped>
.footer-action-btn {
  width: 3rem;
  height: 3rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  line-height: 1;
}

.footer-action-icon {
  flex-shrink: 0;
}
</style>
