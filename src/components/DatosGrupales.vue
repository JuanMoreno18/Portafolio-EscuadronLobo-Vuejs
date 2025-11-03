<script setup>
import linkedin from '/src/assets/linkedin_icon.svg'
import instagram from '/src/assets/instagram_icon.svg'
import github from '/src/assets/github_icon.svg'
import curriculum from '/src/assets/cv_resume_icon.svg'
import FondoLobo from './FondoLobo.vue';
const title = "Escuadron Lobo";
const descripcion = "Estudiantes de la Tecnicatura Universitaria en Programación - UTN";
const residencia = "San Rafael, Mendoza, Argentina";
const presentacion = "Somos un grupo de estudiantes comprometidos con el trabajo en equipo y el aprendizaje constante. A través de proyectos prácticos y colaborativos, aplicamos nuestros conocimientos para desarrollar soluciones creativas y funcionales, preparándonos para los desafíos del mundo profesional.";
const redesociales = [
  { id: 1, name: "linkedin", src: linkedin, url: "https://www.linkedin.com/in/jose-perez/" },
  { id: 2, name: "instagram", src: instagram, url: "https://www.instagram.com/joseperez/" },
  { id: 3, name: "github", src: github, url: "" },
  { id: 4, name: "curriculum", src: curriculum, url: "" },
];
const telefono = "+54 9 2604-056016";
</script>

<template>
  <section class="datos-grupales">
    <FondoLobo />
    <div class="card">
      <div class="card-header">
        <h1>{{ title }}</h1>
        <h2>{{ descripcion }}</h2>
      </div>
      
      <div class="card-body">
        <p class="presentacion">{{ presentacion }}</p>
      </div>
      
      <div class="card-footer">
        <ul class="container-lista">
          <li v-for="red in redesociales" :key="red.id">
            <a :href="red.url" class="social-link" :aria-label="red.name">
              <img class="icon-redsocial" :src="red.src" width="45" :alt="red.name"/>
            </a>
          </li>
        </ul>
        
        <div class="location">
          <span class="location-icon">📍</span>
          <h4>{{ residencia }}</h4>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.datos-grupales {
  display: left;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
  background: #0a0e27;
  position: relative;
}

.card {
  border-radius: 20px;
  padding: 0;
  margin: 20px;
  max-width: 550px;
  width: 100%;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4),
              0 0 0 1px rgba(255, 255, 255, 0.05);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  z-index: 1;
  text-align: center;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 25px 70px rgba(0, 0, 0, 0.5),
              0 0 0 1px rgba(255, 255, 255, 0.1);
}

.card-header {
  background: linear-gradient(135deg, rgba(95, 124, 205, 0.2) 0%, rgba(41, 98, 255, 0.1) 100%);
  padding: 40px 30px 30px;
  border-bottom: 2px solid rgba(95, 124, 205, 0.3);
}

.card-body {
  padding: 35px 40px;
}

.card-footer {
  padding: 30px 40px 40px;
  background: rgba(0, 0, 0, 0.15);
}

.presentacion {
  font-size: 1.15rem;
  font-weight: 400;
  line-height: 1.8;
  color: #e0e6ed;
  margin: 0;
  text-align: justify;
  text-justify: inter-word;
}

h1 {
  font-size: 3rem;
  font-weight: 800;
  background: linear-gradient(135deg, #ffffff 0%, #a8c0ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  transition: all 0.6s ease;
  margin: 0 0 15px 0;
  letter-spacing: -1px;
  text-shadow: 0 2px 20px rgba(95, 124, 205, 0.3);
  cursor: pointer;
  position: relative;
}

h1:hover {
  background: linear-gradient(135deg, #ffffff 0%, #6dd5ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: 0 0 30px rgba(109, 213, 255, 0.8),
              0 0 50px rgba(95, 124, 205, 0.6),
              0 2px 20px rgba(255, 255, 255, 0.4);
  filter: brightness(1.3);
  transform: scale(1.02);
  letter-spacing: 0px;
}

h2 {
  font-size: 1.3rem;
  font-weight: 500;
  color: #a8c0ff;
  margin: 0;
  line-height: 1.5;
  opacity: 0.9;
}

h4 {
  font-size: 1.1rem;
  font-weight: 500;
  color: #c8d6e5;
  margin: 0;
  letter-spacing: 0.5px;
}

p {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.container-lista {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  padding: 0;
  margin: 0 0 25px 0;
  gap: 15px;
  flex-wrap: wrap;
}

.container-lista li {
  display: flex;
  align-items: center;
}

.social-link {
  display: inline-block;
  transition: transform 0.3s ease;
}

.social-link:hover {
  transform: translateY(-5px);
}

.icon-redsocial {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #f0f4ff 0%, #d9e4ff 100%);
  border-radius: 50%;
  padding: 8px;
  box-shadow: 0 4px 15px rgba(95, 124, 205, 0.4),
              inset 0 -2px 5px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  cursor: pointer;
}

.icon-redsocial:hover {
  background: linear-gradient(135deg, #5f7ccd 0%, #2962ff 100%);
  box-shadow: 0 6px 25px rgba(95, 124, 205, 0.6),
              0 0 20px rgba(255, 255, 255, 0.3),
              inset 0 -2px 5px rgba(0, 0, 0, 0.2);
  transform: scale(1.1);
}

.location {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  margin-top: 20px;
  padding: 15px;
  background: rgba(95, 124, 205, 0.1);
  border-radius: 12px;
  border: 1px solid rgba(95, 124, 205, 0.2);
}

.location-icon {
  font-size: 1.5rem;
}

h3 {
  font-size: 1.2rem;
  font-weight: 600;
  color: #e0e6ed;
  margin: 20px 0 10px 0;
}

@media (max-width: 768px) {
    /* ✨ AJUSTE ADICIONAL para asegurar la alineación de la presentación 
    (Si queremos que el texto justificado se vea mejor en móviles, lo centramos o alineamos a la izquierda) 
    */
    .presentacion {
        text-align: left; /* Mantenemos la alineación a la izquierda para mejor lectura en móviles */
    }

    /* Reducir el padding horizontal de la tarjeta para evitar que se pegue demasiado a los bordes */
    .card {
        margin-left: 10px;
        margin-right: 10px;
    }

    /* Ajustes de tamaño y padding para móvil */
    h1 {
        font-size: 2.2rem;
    }
    
    h2 {
        font-size: 1.1rem;
    }
    
    .card-header,
    .card-body,
    .card-footer {
        padding: 25px 20px;
    }
    
    .icon-redsocial {
        width: 40px; /* Ligeramente más pequeños */
        height: 40px;
        padding: 6px;
    }

    .container-lista {
        gap: 10px; /* Reducir el espacio entre íconos */
    }
}
</style>