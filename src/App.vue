<script setup>

import NavBar from './components/icons/NavBar.vue';
import DatosGrupales from './components/DatosGrupales.vue';
import IntegrantesComponente from './components/IntegrantesComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponente from './components/HabilidadesComponente.vue';

</script>

<template>
  <header>
     <!-- barra de navegacion -->
    <NavBar />
    <!-- componente Datos peronales -->
     <DatosGrupales /> 
  </header>
  <main>
      <section id="Integrantes"><h2></h2><IntegrantesComponente /></section>
      <section id="proyectos"><h2>Proyectos</h2><ProyectosComponente /></section>
      <section id="habilidades"><h2>Habilidades</h2><HabilidadesComponente /></section>


  </main>
 <section class="contacto-contenedor" id="contacto">
    <h2>Contáctanos</h2>
    <div class="formulario-wrapper">
      <iframe 
        src="https://docs.google.com/forms/d/e/1FAIpQLSflpJTvLVW0u7D-7m56dBMZho1iApyBDF2dxX9rF0E2f1eBtA/viewform?embedded=true"
        width="100%" 
        height="800" 
        frameborder="0" 
        marginheight="0" 
        marginwidth="0">
        Cargando formulario…
      </iframe>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <a href="id = aTop">Inicio</a>
    <p>© 2025 Escuadron Lobo - Portafolio web</p>
  </footer>

  <!-- Botón flotante (ya lo tienes en App.vue) -->
  <a href="#contacto" class="boton-flotante-contacto" title="Contacto">
  <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
    <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
  </svg>
  <span>Contacto</span>
</a>

</template>
<style>
body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  background: linear-gradient(-45deg, #020916, #0c1a2e, #0f1f38, #08121f, #111e33, #040d1a);
  background-size: 400% 400%;
  animation: gradientShift 20s ease infinite;
  position: relative;
  overflow-x: hidden;
}

/* Capa de brillo sutil */
body::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: 
    radial-gradient(circle at 20% 30%, rgba(59, 130, 246, 0.08) 0%, transparent 40%),
    radial-gradient(circle at 80% 70%, rgba(30, 64, 175, 0.06) 0%, transparent 45%),
    radial-gradient(circle at 50% 50%, rgba(37, 99, 235, 0.04) 0%, transparent 60%);
  pointer-events: none;
  z-index: 0;
  animation: pulseGlow 12s ease-in-out infinite;
}

/* Efecto de estrellas/partículas */
body::after {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    radial-gradient(2px 2px at 20% 30%, rgba(255, 255, 255, 0.15), transparent),
    radial-gradient(2px 2px at 60% 70%, rgba(255, 255, 255, 0.1), transparent),
    radial-gradient(1px 1px at 50% 50%, rgba(255, 255, 255, 0.1), transparent),
    radial-gradient(1px 1px at 80% 10%, rgba(255, 255, 255, 0.15), transparent),
    radial-gradient(2px 2px at 90% 60%, rgba(255, 255, 255, 0.1), transparent),
    radial-gradient(1px 1px at 33% 85%, rgba(255, 255, 255, 0.1), transparent);
  background-size: 200% 200%;
  pointer-events: none;
  z-index: 0;
  opacity: 0.3;
  animation: starsMove 30s linear infinite;
}

@keyframes gradientShift {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes pulseGlow {
  0%, 100% {
    opacity: 0.5;
    transform: scale(1);
  }
  50% {
    opacity: 0.8;
    transform: scale(1.05);
  }
}

@keyframes starsMove {
  0% {
    background-position: 0% 0%;
  }
  100% {
    background-position: 100% 100%;
  }
}

#app {
  min-height: 100vh;
  background: transparent;
  position: relative;
  z-index: 1;
}
</style>
<style scoped>
footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    font-size: 1.3rem;
}
footer a {
    display: inline-block;
    padding: 0.8rem 2rem;
    margin-bottom: 1rem;
    color: #00ff88;
    text-decoration: none;
    border: 2px solid #00ff88;
    border-radius: 25px;
    font-weight: 600;
    transition: all 0.3s ease;
}

footer a:hover {
    background: rgba(0, 255, 136, 0.1);
    box-shadow: 0 0 20px rgba(0, 255, 136, 0.6),
                0 0 40px rgba(0, 255, 136, 0.3);
    transform: translateY(-3px);
}

.boton-flotante-contacto {
  position: fixed;
  bottom: 30px;
  right: 30px;
  padding: 15px 25px;
  background: linear-gradient(135deg, #00ff88 0%, #00cc6a 100%);
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  box-shadow: 0 4px 15px rgba(0, 255, 136, 0.4);
  cursor: pointer;
  transition: all 0.3s ease;
  z-index: 1000;
  color: #001a0d;
  text-decoration: none;
  font-weight: 600;
  font-size: 1.1rem;
}

.boton-flotante-contacto:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 20px rgba(0, 255, 136, 0.6);
  background: linear-gradient(135deg, #00cc6a 0%, #00ff88 100%);
}

.boton-flotante-contacto svg {
  width: 28px;
  height: 28px;
}

.boton-flotante-contacto span {
  color: #001a0d;
}

</style>
