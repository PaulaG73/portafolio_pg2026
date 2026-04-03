<template>
  <div class="navBar">
    <nav class="navbar navbar-expand-lg bg-success navbar-dark py-2 py-md-4 fixed-top shadow-sm">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Paula Gajardo Schmidlin</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" href="#sobre-mi">Sobre mí</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#habilidades">Habilidades</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#proyectos">Proyectos</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#contacto">Contacto</a>
            </li>
          </ul>

          <button
            type="button"
            class="btn btn-outline-light btn-sm d-flex align-items-center gap-1 cv-btn"
            data-bs-toggle="modal"
            data-bs-target="#cvModal"
            title="Ver CV"
            aria-label="Ver CV en PDF sobre esta página"
          >
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
              <path d="M14 4.5V14a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V2a2 2 0 0 1 2-2h5.5L14 4.5zm-3 0A1.5 1.5 0 0 1 9.5 3V1H4a1 1 0 0 0-1 1v12a1 1 0 0 0 1 1h8a1 1 0 0 0 1-1V4.5h-2z"/>
              <path d="M4.603 14.087a.81.81 0 0 1-.438-.42c-.195-.388-.13-.776.08-1.102.198-.307.526-.568.897-.787a7.68 7.68 0 0 1 1.482-.645 19.697 19.697 0 0 0 1.062-2.227 7.269 7.269 0 0 1-.43-1.295c-.086-.4-.119-.796-.046-1.136.075-.354.274-.672.65-.823.192-.077.4-.12.602-.077a.7.7 0 0 1 .477.365c.088.164.12.356.127.538.007.188-.012.396-.047.614-.084.51-.27 1.134-.52 1.794a10.954 10.954 0 0 0 .98 1.686 5.753 5.753 0 0 1 1.334.05c.364.066.734.195.96.465.12.144.193.32.2.518.007.192-.047.382-.138.563a1.04 1.04 0 0 1-.354.416.856.856 0 0 1-.51.138c-.331-.014-.654-.196-.933-.417a5.712 5.712 0 0 1-.911-.95 11.651 11.651 0 0 0-1.997.406 11.307 11.307 0 0 1-1.02 1.51c-.292.35-.609.656-.927.787a.793.793 0 0 1-.58.029zm1.379-1.901c-.166.076-.32.156-.459.238-.328.194-.541.383-.647.547-.094.145-.096.25-.04.361.01.022.02.036.026.044a.266.266 0 0 0 .035-.012c.137-.056.355-.235.635-.572a8.18 8.18 0 0 0 .45-.606zm1.64-1.33a12.71 12.71 0 0 1 1.01-.193 11.744 11.744 0 0 1-.51-.858 20.801 20.801 0 0 1-.5 1.05zm2.446.45c.15.163.296.3.435.41.24.19.407.253.498.256a.107.107 0 0 0 .07-.015.307.307 0 0 0 .094-.125.436.436 0 0 0 .059-.2.095.095 0 0 0-.026-.063c-.052-.062-.2-.152-.518-.209a3.876 3.876 0 0 0-.612-.053zM8.078 7.8a6.7 6.7 0 0 0 .2-.828c.031-.188.043-.343.038-.465a.613.613 0 0 0-.032-.198.517.517 0 0 0-.145.04c-.087.035-.158.106-.196.283-.04.192-.03.469.046.822.024.111.054.227.09.346z"/>
            </svg>
            CV
          </button>

        </div>
      </div>
    </nav>

    <div
      id="cvModal"
      class="modal fade cv-pdf-overlay"
      tabindex="-1"
      aria-labelledby="cvModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-fullscreen-lg-down modal-dialog-centered cv-pdf-dialog">
        <div class="modal-content border-0 bg-white cv-pdf-sheet">
          <h2 id="cvModalLabel" class="visually-hidden">Curriculum vitae (PDF)</h2>

          <div class="cv-pdf-toolbar d-flex d-lg-none align-items-stretch gap-2 px-2 py-2 bg-success shadow-sm">
            <button
              type="button"
              class="btn btn-light btn-sm fw-semibold flex-grow-1 text-success"
              data-bs-dismiss="modal"
            >
              ← Volver al portafolio
            </button>
            <button
              type="button"
              class="btn btn-outline-light btn-sm px-2"
              data-bs-dismiss="modal"
              aria-label="Cerrar"
            >
              <span class="lh-1" aria-hidden="true">✕</span>
            </button>
          </div>

          <button
            type="button"
            class="btn-close cv-pdf-close d-none d-lg-block"
            data-bs-dismiss="modal"
            aria-label="Cerrar y volver al portafolio"
          ></button>

          <iframe
            :src="cvPdfEmbedSrc"
            title="CV Paula Gajardo Schmidlin (PDF)"
            class="cv-pdf-frame"
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const cvPdfUrl = `${process.env.BASE_URL}CV_Paula_Gajardo_Schmidlin.pdf`
/* Ajuste al ancho del visor (Chrome/Edge); el marco de la página es blanco, no gris */
const cvPdfEmbedSrc = `${cvPdfUrl}#view=FitH`
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar-brand,
.nav-link {
  font-family: 'Playfair Display', Georgia, serif;
}

.navbar-brand {
  font-size: 1.3rem;
}

.cv-btn {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 0.85rem;
  white-space: nowrap;
}

.cv-pdf-overlay .cv-pdf-sheet {
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: hidden;
  min-height: 100%;
}

.cv-pdf-overlay .cv-pdf-dialog {
  margin-top: env(safe-area-inset-top, 0);
  margin-bottom: env(safe-area-inset-bottom, 0);
}

.cv-pdf-frame {
  flex: 1 1 auto;
  width: 100%;
  min-height: 0;
  border: 0;
  background: #fff;
}

/* Escritorio: PDF “flotante” pero grande para leer cómodo */
@media (min-width: 992px) {
  .cv-pdf-overlay .cv-pdf-dialog {
    width: min(97vw, 1680px);
    max-width: min(97vw, 1680px);
    margin-left: auto;
    margin-right: auto;
  }

  .cv-pdf-overlay .cv-pdf-sheet {
    min-height: 0;
    height: min(92vh, 1400px);
    border-radius: 0.75rem;
    box-shadow:
      0 0.5rem 1.5rem rgba(0, 0, 0, 0.35),
      0 1.25rem 3rem rgba(0, 0, 0, 0.22);
    outline: 1px solid rgba(0, 0, 0, 0.06);
  }

  .cv-pdf-close {
    position: absolute;
    top: 0.5rem;
    right: 1.15rem;
    z-index: 1090;
    padding: 0.5rem;
    margin: 0;
    background-color: rgba(255, 255, 255, 0.95);
    border-radius: 50%;
    box-shadow: 0 1px 6px rgba(0, 0, 0, 0.12);
    opacity: 1;
  }

  .cv-pdf-close:hover {
    background-color: #fff;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.18);
  }
}

/* Notebook: un poco más compacto que monitores grandes */
@media (min-width: 992px) and (max-width: 1599.98px),
  (min-width: 992px) and (max-height: 950px) {
  .cv-pdf-overlay .cv-pdf-dialog {
    width: min(91vw, 1320px);
    max-width: min(91vw, 1320px);
  }

  .cv-pdf-overlay .cv-pdf-sheet {
    height: min(86vh, 960px);
  }
}

/* Móvil / tablet: casi todo el alto; barra superior ya indica cómo volver */
@media (max-width: 991.98px) {
  .cv-pdf-overlay .cv-pdf-sheet {
    min-height: 100%;
    border-radius: 0;
  }

  .cv-pdf-toolbar {
    flex-shrink: 0;
    z-index: 1090;
  }
}
</style>

<!-- Backdrop: en grande se atenúa el portafolio; en chico más cubriente -->
<style>
body.modal-open .modal-backdrop.show {
  background-color: #1a2f24;
}

@media (min-width: 992px) {
  body.modal-open .modal-backdrop.show {
    opacity: 0.55;
  }
}

@media (max-width: 991.98px) {
  body.modal-open .modal-backdrop.show {
    opacity: 0.92;
  }
}
</style>
