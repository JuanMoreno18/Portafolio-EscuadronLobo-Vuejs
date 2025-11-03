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
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  padding: 20px;
  justify-items: center;
  background: linear-gradient(-45deg, #e21526, #03346E, #6EACDA, #E2E2B6);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
}

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
  height: 180px;
  object-fit: cover;
  display: block;
}

.proyecto-info {
  padding: 15px;
  text-align: center;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
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
  flex-grow: 1;
}

/* Enlaces */
.proyecto-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: auto;
  padding-top: 10px;
}

.btn-ver-mas {
  background-color: #007BFF;
  color: #fff;
  padding: 10px 15px;
  border-radius: 6px;
  text-decoration: none;
  transition: background-color 0.3s ease;
  font-size: 0.9em;
}

.btn-ver-mas:hover {
  background-color: #0056b3;
}

.github-link {
  color: #333;
  text-decoration: none;
  font-size: 0.9em;
  padding: 8px;
}

.github-link:hover {
  text-decoration: underline;
  color: #007BFF;
}

/* ----- RESPONSIVE ----- */

/* Tablets */
@media (max-width: 768px) {
  .galeria {
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
    padding: 15px;
  }

  .proyecto {
    max-width: 100%;
  }
}

/* Celulares 375px - 424px */
@media (min-width: 375px) and (max-width: 425px) {
  .galeria {
    grid-template-columns: repeat(2, 1fr);
    gap: 8px;
    padding: 2px;
  }

  .proyecto {
    max-width: 95%;
    border-radius: 8px;
  }

  .proyecto img {
    height: 120px;
  }

  .proyecto-info {
    padding: 1px;
  }

  .proyecto-info h3 {
    font-size: 1em;
    margin: 0px 0;
  }

  .proyecto-info p {
    font-size: 0.85em;
    margin: 0px 0;
    line-height: 1.3;
  }

  .proyecto-links {
    gap: 0px;
    margin-top: 2px;
  }

  .btn-ver-mas {
    padding: 6px 10px;
    font-size: 0.85em;
  }

  .github-link {
    font-size: 0.8em;
    padding: 6px;
  }
}

/* Celulares pequeños (menos de 375px) */
@media (max-width: 374px) {
  .galeria {
    grid-template-columns: 1fr;
    gap: 15px;
    padding: 10px;
  }

  .proyecto {
    max-width: 100%;
  }

  .proyecto img {
    height: 160px;
  }

  .proyecto-info {
    padding: 12px;
  }

  .proyecto-info h3 {
    font-size: 1.1em;
  }

  .proyecto-info p {
    font-size: 0.9em;
  }
}

/* Computadoras → 4 columnas */
@media (min-width: 1024px) {
  .galeria {
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    padding: 25px;
  }

  .proyecto {
    max-width: 300px;
  }

  .proyecto img {
    height: 200px;
  }
}
</style>