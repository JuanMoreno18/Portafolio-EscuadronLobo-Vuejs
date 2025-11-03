<script setup>
import { ref } from 'vue';
import FondoObjetos from './FondoObjetos.vue';
import DarioImg from '@/assets/Dario.png';
import MatiasImg from '@/assets/matias.png';
import OrlandoImg from '@/assets/Orlando.png';
import ValeriaImg from '@/assets/valeria.png';
import JuanImg from '@/assets/juan.png';
import CeciliaImg from '@/assets/cecilia.png';
import ValentinImg from '@/assets/valentin.png';
import LucasImg from '@/assets/lucas.png';

// Array de integrantes del equipo
const integrantes = ref([
  {
    id: 1,
    nombre: 'Lucas Aguilar',
    //rol: 'Full Stack Developer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/Luklas7u7',
    linkedin: 'https://linkedin.com/in/juanperez',
    imagen: LucasImg,
  },
  {
    id: 2,
    nombre: 'Matias Altamiranda',
    //rol: 'Frontend Developer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/mathias5525',
    linkedin: 'https://linkedin.com/in/mariagonzalez',
    imagen: MatiasImg,
  },
  {
    id: 3,
    nombre: 'Valentin Bertolone',
    //rol: 'Backend Developer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/Valentin-bertolone',
    linkedin: 'https://linkedin.com/in/carlosrodriguez',
    imagen: ValentinImg,
  },
  {
    id: 4,
    nombre: 'Cecilia Farias',
    //rol: 'DevOps Engineer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/Cecy-Fa',
    linkedin: 'https://linkedin.com/in/anamartinez',
    imagen: CeciliaImg,
  },
  {
  id: 5,
    nombre: 'Juan Moreno',
    //rol: 'DevOps Engineer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/JuanMoreno18',
    linkedin: 'https://linkedin.com/in/anamartinez',
    imagen: JuanImg,
  },
  {
  id: 6,
    nombre: 'Valeria Pinaya',
    //rol: 'DevOps Engineer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/ValeriaPinaya',
    linkedin: 'https://linkedin.com/in/anamartinez',
    imagen: ValeriaImg,
  },
   {
  id: 7,
    nombre: 'Dario Scilipoti',
    //rol: 'DevOps Engineer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/dariosci',
    linkedin: 'https://linkedin.com/in/anamartinez',
    imagen: DarioImg,
  },
   {
  id: 8,
    nombre: 'Orlando Zelada',
    //rol: 'DevOps Engineer',
    descripcion: 'Estudiante de la tecnicatura en programacion de la UTN San Rafael.',
    github: 'https://github.com/ZeladaG940',
    linkedin: 'https://linkedin.com/in/anamartinez',
    imagen: OrlandoImg,
   }

]);
</script>

<template>
  <div class="integrantes-contenedor" id="integrantes">
    <!-- Fondo animado -->
    <FondoObjetos />

    <!-- Contenido encima del fondo -->
    <div class="contenido">
      <h2 class="titulo">Nuestro Equipo</h2>
      
      <div class="grid-integrantes">
        <div 
          class="card-integrante" 
          v-for="integrante in integrantes" 
          :key="integrante.id"
        >
          <div class="imagen-contenedor">
            <img 
              :src="integrante.imagen" 
              :alt="integrante.nombre"
              class="foto"
            />
          </div>
          
          <div class="info">
            <h3 class="nombre">{{ integrante.nombre }}</h3>
            <p class="rol">{{ integrante.rol }}</p>
            <p class="descripcion">{{ integrante.descripcion }}</p>
            
            <div class="redes-sociales">
  <a 
    :href="integrante.github" 
    target="_blank" 
    rel="noopener noreferrer"
    class="enlace-red"
    title="GitHub"
  >
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
      <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
    </svg>
  </a>
  
  <a 
    :href="integrante.linkedin" 
    target="_blank" 
    rel="noopener noreferrer"
    class="enlace-red"
    title="Perfil profesional"
  >
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
      <path d="M20 3H4c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM8 19H5V9h3v10zM6.5 7.5C5.67 7.5 5 6.83 5 6s.67-1.5 1.5-1.5S8 5.17 8 6s-.67 1.5-1.5 1.5zM19 19h-3v-5.5c0-3.03-4-2.8-4 0V19h-3V9h3v1.5c1.4-2.59 7-2.78 7 2.48V19z"/>
    </svg>
  </a>
</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.integrantes-contenedor {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  max-width: 100%;
  padding: 3rem 2rem;
  min-height: 100vh;
  overflow: hidden;
}

.integrantes-contenedor :deep(.fondo-lava) {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.contenido {
  position: relative;
  z-index: 1;
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
}

.titulo {
  text-align: center;
  font-size: 2.5rem;
  color: var(--vt-c-white-soft);
  margin-bottom: 2rem;
  text-shadow: 3px 3px 6px rgba(0, 0, 0, 1);
  font-weight: bold;
}

.grid-integrantes {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.2rem;
  padding: 1rem;
  width: 100%;
  margin: 0 auto;
}

.card-integrante {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px !important;
  padding: 1rem;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  aspect-ratio: 0.75; 
  overflow: hidden;
  -webkit-border-radius: 20px;
  -moz-border-radius: 20px;
}

.card-integrante:hover {
  transform: translateY(-10px);
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.3);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.imagen-contenedor {
  width: 65px;
  height: 65px;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 0.6rem;
  border: 2px solid rgba(255, 255, 255, 0.3);
  transition: border-color 0.3s ease;
  flex-shrink: 0;
}

.card-integrante:hover .imagen-contenedor {
  border-color: rgba(255, 255, 255, 0.6);
}

.foto {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.info {
  width: 100%;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.nombre {
  font-size: 0.95rem;
  color: var(--vt-c-white-soft);
  margin-bottom: 0.3rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
  font-weight: 600;
}

.rol {
  font-size: 0.8rem;
  color: #4fc3f7;
  margin-bottom: 0.5rem;
  font-weight: 500;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
}

.descripcion {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.3;
  margin-bottom: 0.8rem;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.8);
  flex-grow: 1;
}

.redes-sociales {
  display: flex;
  gap: 0.8rem;
  justify-content: center;
  margin-top: auto;
  padding-top: 0.5rem;
}

.enlace-red {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.15);
  color: var(--vt-c-white-soft);
  transition: all 0.3s ease;
  text-decoration: none;
}

.enlace-red:hover {
  background: rgba(0, 255, 136, 0.3);
  transform: scale(1.15);
  box-shadow: 0 0 15px rgba(0, 255, 136, 0.5);
}

.enlace-red svg {
  width: 22px;
  height: 22px;
  fill: currentColor;
}

/* Tablets */
@media (max-width: 768px) {
  .titulo {
    font-size: 3rem;
  }

  .grid-integrantes {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .integrantes-contenedor {
    padding: 2rem 1.5rem;
  }
  .nombre {
    font-size: 1.2rem;
    margin-bottom: 0.2rem;
  }

  .card-integrante {
    padding: 3rem;
    aspect-ratio: 0.9;
  }

  .enlace-red {
    width: 38px;
    height: 38px;
  }

  .enlace-red svg {
    width: 20px;
    height: 20px;
  }
}

/* Celulares 425px */
@media (max-width: 425px) {
  .titulo {
    font-size: 1.8rem;
    margin-bottom: 1.5rem;
  }

  .grid-integrantes {
    grid-template-columns: repeat(2, 1fr);
    gap: 0.8rem;
    padding: 0.5rem;
  }

  .card-integrante {
    padding: 0rem;
    border-radius: 15px !important;
    aspect-ratio: 0.58; /* Más alto en móviles */
  }

  .imagen-contenedor {
    width: 55px;
    height: 55px;
    margin-bottom: 0.5rem;
  }

  .nombre {
    font-size: 0.8rem;
    margin-bottom: 0.2rem;
  }

  .rol {
    font-size: 0.72rem;
    margin-bottom: 0.4rem;
  }

  .descripcion {
    font-size: 0.65rem;
    line-height: 1.25;
    margin-bottom: 0.6rem;
  }

  .redes-sociales {
    gap: 0.7rem;
  }

  .enlace-red {
    width: 36px;
    height: 36px;
  }

  .enlace-red svg {
    width: 19px;
    height: 19px;
  }

  .integrantes-contenedor {
    padding: 1.5rem 0.8rem;
  }
}

/* Celulares pequeños */
@media (min-width: 375px) and (max-width: 424px) {
  .titulo {
    font-size: 1.1rem;
  }

  .grid-integrantes {
    gap: 0rem;
    padding: 0.1rem;
  }

  .card-integrante {
    padding: 0rem;
    aspect-ratio: 0.65;
  }

  .imagen-contenedor {
    width: 40px;
    height: 40px;
  }

  .nombre {
    font-size: 0.60rem;
  }

  .descripcion {
    font-size: 0.55rem;
  }

  .enlace-red {
    width: 28px;
    height: 28px;
  }

  .enlace-red svg {
    width: 16px;
    height: 16px;
  }
  
  /* Celulares mas pequeños */
  @media (max-width: 320px) {
  .titulo {
    font-size: 1rem;
  }

  .grid-integrantes {
    gap: 0rem;
    padding: 0.1rem;
  }

  .card-integrante {
    padding: 0rem;
    aspect-ratio: 0.45;
  }

  .imagen-contenedor {
    width: 40px;
    height: 40px;
  }

  .nombre {
    font-size: 0.60rem;
  }

  .descripcion {
    font-size: 0.55rem;
  }

  .enlace-red {
    width: 28px;
    height: 28px;
  }

  .enlace-red svg {
    width: 16px;
    height: 16px;
  }
}
}
</style>