<script setup>
import Proyecto1 from '/src/assets/vueProyecto.jpg'
import Proyecto2 from '/src/assets/reactProyecto.jpg'
import Proyecto3 from '/src/assets/flutterProyecto.png'
import Proyecto4 from '/src/assets/chartProyecto.jpg'
import { ref } from 'vue'

const misProyectos = ref([
  {
    id: 1,
    src: Proyecto1,
    titulo: "Sistema de Gestión de Inventario (2024)",
    descripcion: "Aplicación web con Vue.js y Node.js para control de stock en tiempo real, con alertas automáticas y reportes detallados.",
    projectoLink: "https://www.google.com.ar",
    githublink: "https://github.com/usuario/proyecto"
  },
  {
    id: 2,
    src: Proyecto2,
    titulo: "Plataforma E-Learning Interactiva (2023)",
    descripcion: "Plataforma educativa con React que permite a los profesores subir contenido y hacer seguimiento del progreso de los estudiantes.",
    projectoLink: "https://www.google.com.ar",
    githublink: "https://github.com/usuario/proyecto"
  },
  {
    id: 3,
    src: Proyecto3,
    titulo: "App de Gestión de Tareas Colaborativas (2023)",
    descripcion: "Aplicación móvil con Flutter para equipos de trabajo, con tableros Kanban y sincronización en la nube.",
    projectoLink: "https://www.google.com.ar",
    githublink: "https://github.com/usuario/proyecto"
  },
  {
    id: 4,
    src: Proyecto4,
    titulo: "Dashboard Analítico en Tiempo Real (2024)",
    descripcion: "Panel de control con visualización de datos en tiempo real usando Chart.js y WebSockets.",
    projectoLink: "https://www.google.com.ar",
    githublink: "https://github.com/usuario/proyecto"
  },
])
</script>

<template>
  <div class="galeria">
    <div class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
      <img :src="proyecto.src" :alt="proyecto.titulo" />
      <div class="proyecto-info">
        <h3>{{ proyecto.titulo }}</h3>
        <p>{{ proyecto.descripcion }}</p>
        <div class="proyecto-links">
          <a :href="proyecto.projectoLink" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
          <a :href="proyecto.githublink" class="github-link" target="_blank" rel="noopener noreferrer">Ver Código en GitHub</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.galeria {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /* base adaptable */
  gap: 20px;
  padding: 20px;
  justify-items: center;
  background: linear-gradient(-45deg, #e21526, #03346E, #6EACDA, #E2E2B6);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
}

/* Animación de fondo */
@keyframes gradient {
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

/* ----- TARJETA DEL PROYECTO ----- */
.proyecto {
  display: flex;
  flex-direction: column;
  border: 2px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
  background-color: #f9f9f9;
  width: 100%;
  max-width: 280px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.proyecto:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
}

.proyecto img {
  width: 100%;
  height: auto;
  display: block;
}

.proyecto-info {
  padding: 15px;
  text-align: center;
}

.proyecto-info h3 {
  margin: 10px 0;
  font-size: 1.2em;
  color: #333;
}

.proyecto-info p {
  font-size: 0.95em;
  color: #666;
  margin: 10px 0;
}

/* Enlaces */
.proyecto-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 10px;
}

.btn-ver-mas {
  background-color: #007BFF;
  color: #fff;
  padding: 10px 15px;
  border-radius: 6px;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.btn-ver-mas:hover {
  background-color: #0056b3;
}

.github-link {
  color: #333;
  text-decoration: none;
  font-size: 0.9em;
}

.github-link:hover {
  text-decoration: underline;
}

/* ----- RESPONSIVE ----- */


@media (max-width: 768px) {
  .galeria {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* 🖥️ Computadoras → 4 columnas */
@media (min-width: 1024px) {
  .galeria {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
