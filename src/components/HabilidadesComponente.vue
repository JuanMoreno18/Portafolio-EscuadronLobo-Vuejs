<script setup>
import img1 from '/src/components/icons/js.svg'
import img2 from '/src/components/icons/python.svg'
import img3 from '/src/components/icons/html-css.svg'
import img4 from '/src/components/icons/java.svg'
import img5 from '/src/components/icons/sql.svg'
import img6 from '/src/components/icons/react.svg'
import img7 from '/src/components/icons/vue.svg'
import img8 from '/src/components/icons/node.svg'
import img9 from '/src/components/icons/django.svg'
import img10 from '/src/components/icons/bootstrap.svg'
import img11 from '/src/components/icons/git.svg'
import img12 from '/src/components/icons/docker.svg'
import img13 from '/src/components/icons/cypress.svg'
import img14 from '/src/components/icons/figma.svg'
import img15 from '/src/components/icons/visual.svg'
import img16 from '/src/components/icons/mongo.svg'
import img17 from '/src/components/icons/mysql.svg'
import img18 from '/src/components/icons/postgres.svg'
import img19 from '/src/components/icons/arg.svg'
import img20 from '/src/components/icons/eeuu.svg'
//Se importa ref de vue para poder usarlo
import { ref } from 'vue';
//Se crea un array de objetos con las habilidades
//Este es un array de objetos con habilidades que se pueden modificar o agregar
const habilidades = ref([
    {// Se crea un objeto con id, nombre y habilidades
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            //se crea un objeto con id, nombre, nivel e icono
            { id: 1, nombre: 'JavaScript', nivel: 'Avanzado', icono: img1 },
            { id: 2, nombre: 'Python', nivel: 'Intermedio', icono: img2 },
            { id: 3, nombre: 'HTML/CSS', nivel: 'Avanzado', icono: img3 },
            { id: 4, nombre: 'Java', nivel: 'Intermedio', icono: img4 },
            { id: 5, nombre: 'SQL', nivel: 'Intermedio', icono: img5 }
        ]
    },
    {
        id: 2, nombre: 'Frameworks y Librerías', habilidades: [
            { id: 1, nombre: 'React.js', nivel: 'Avanzado', icono: img6 },
            { id: 2, nombre: 'Vue.js', nivel: 'Intermedio', icono: img7 },
            { id: 3, nombre: 'Node.js', nivel: 'Avanzado', icono: img8 },
            { id: 4, nombre: 'Django', nivel: 'Intermedio', icono: img9 },
            { id: 5, nombre: 'Bootstrap', nivel: 'Avanzado', icono: img10 }
        ]
    },
    {
        id: 3, nombre: 'Herramientas y Software', habilidades: [
            { id: 1, nombre: 'Git', nivel: 'Avanzado', icono: img11 },
            { id: 2, nombre: 'Docker', nivel: 'Intermedio', icono: img12 },
            { id: 3, nombre: 'Cypress', nivel: 'Intermedio', icono: img13 },
        { id: 4, nombre: 'Figma', nivel: 'Intermedio', icono: img14 },
            { id: 5, nombre: 'Visual Studio Code', nivel: 'Avanzado', icono: img15 }
        ]
    },
    {
        id: 4, nombre: 'Bases de Datos', habilidades: [
            { id: 1, nombre: 'MongoDB', nivel: 'Avanzado', icono: img16 },
            { id: 2, nombre: 'MySQL', nivel: 'Intermedio', icono: img17 },
            { id: 3, nombre: 'PostgreSQL', nivel: 'Intermedio', icono: img18 }
        ]
    },
    {
        id: 5, nombre: 'Idiomas', habilidades: [
            { id: 1, nombre: 'Español', nivel: 'Nativo', icono: img19 },
            { id: 2, nombre: 'Inglés', nivel: 'Avanzado (C1)', icono: img20 }
        ]
    }
]);

</script>

<template>
    <!-- Este componente Vue funciona de esta forma:-->
    <div class="skills-contenedor">
        <!--Se recorre el array habilidades con v-for y se asigna la key habilidad.id-->
        <div v-for="habilidad in habilidades" :key="habilidad.id" class="skills-categoria">
            <!--Se muestra el nombre de la habilidad-->
            <h3>{{ habilidad.nombre }}</h3>
            <ul class="skills">
                <!--Se recorre el array habilidades con v-for y se asigna la key habilidad.id-->
                <li v-for="habilidad in habilidad.habilidades" :key="habilidad.id" class="skill">
                    <!--Se muestra el icono de la habilidad con el nombre de la habilidad con su nivel-->
                    <img :src="habilidad.icono" :alt="habilidad.nombre">
                    <!--Se muestra el icono de la habilidad y el nombre de la habilidad con su nivel-->
                    <span>{{ habilidad.nombre }}: {{ habilidad.nivel }}</span>
                </li>
            </ul>
        </div>
    </div>
    <!-- <div class="skills-contenedor">
        <div class="skills-categoria">
            <h3>Lenguajes de Programación</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/js.svg" alt="JavaScript">
                    <span>JavaScript: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/python.svg" alt="Python">
                    <span>Python: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/html-css.svg" alt="HTML/CSS">
                    <span>HTML/CSS: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/java.svg" alt="Java">
                    <span>Java: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/sql.svg" alt="SQL">
                    <span>SQL: Intermedio</span>
                </li>
            </ul>
        </div>

    </div>

    <div class="skills-categoria">
            <h3>Frameworks y Librerías</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/react.svg" alt="React.js">
                    <span>React.js: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/vue.svg" alt="Vue.js">
                    <span>Vue.js: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/node.svg" alt="Node.js">
                    <span>Node.js: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/django.svg" alt="Django">
                    <span>Django: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/bootstrap.svg" alt="Bootstrap">
                    <span>Bootstrap: Avanzado</span>
                </li>
            </ul>
    </div>

    <div class="skills-categoria">
            <h3>Herramientas y Software</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/git.svg" alt="Git">
                    <span>Git: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/docker.svg" alt="Docker">
                    <span>Docker: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/cypress.svg" alt="Cypress">
                    <span>Cypress: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/figma.svg" alt="Figma">
                    <span>Figma: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/visual.svg" alt="Visual Studio Code">
                    <span>Visual Studio Code: Avanzado</span>
                </li>
            </ul>
    </div>
    <div class="skills-categoria">
            <h3>Bases de Datos</h3>
            <ul class="skills">
                <div class="skill">
                    <img src="/src/components/icons/mongo.svg" alt="MongoDB">
                    <span>MongoDB: Avanzado</span>
                </div>
                <div class="skill">
                    <img src="/src/components/icons/mysql.svg" alt="MySQL">
                    <span>MySQL: Intermedio</span>
                </div>
                <div class="skill">
                    <img src="/src/components/icons/postgres.svg" alt="PostgreSQL">
                    <span>PostgreSQL: Intermedio</span>
                </div>
            </ul>
    </div>

        <div class="skills-categoria">
            <h3>Idiomas</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/arg.svg" alt="Español">
                    <span>Español: Nativo</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/eeuu.svg" alt="Inglés">
                    <span>Ingles Avanzado</span>
                </li>
            </ul>
        </div> -->
</template>

<style scoped>
.skills-contenedor {
    padding: 2rem;
    /*Fondo cargado desde una imagen estatica en Assets*/
    /* background-image: url('/src/assets/fondo-proyectos.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat; */
    /*Fondo con gradiente*/
    /* background: linear-gradient(-45deg, #e21526, #03346E, #6EACDA, #E2E2B6); */
    /*Fondo con color solido*/
    /* background-color: rgb(28, 41, 52); */
}

.skills-categoria {
    margin-bottom: 20px;
}

.skills-categoria h3 {
    display: flex;
    justify-content: left;
    margin-bottom: 10px;
    font-size: 1.5em;
    color: aliceblue;
    font-size: 1.5em;
    font-weight: bold;
}

.skills {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    gap: 20px;
}

.skill {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgba(241, 245, 243, 0.856);
    padding: 0.3em;
    border-radius: 8px;
    box-shadow: 0px 4px 12px rgba(2, 151, 151, 0.963);
    flex: 1 1 200px;
    max-width: 250px;
}

.skill:hover {
    background-color: rgba(2, 151, 151, 0.963);
}

.skill img {
    width: 35px;
    height: 35px;
}

.skill span {
    font-size: 1em;
    color: #333;
}

.skill:hover {
    font-size: 1em;
    transition: 1s ease;
}

/* Tablets */
@media (max-width: 768px) {
  .skills-contenedor {
    padding: 1.5rem;
  }

  .skills {
    gap: 0.8rem;
    justify-content: center;
  }

  .skill {
    flex: 1 1 calc(30% - 0.8rem);
    max-width: none;
    min-width: 120px;
    padding: 0.6em;
  }

  .skill img {
    width: 30px;
    height: 30px;
  }

  .skill span {
    font-size: 0.85em;
  }

  .skills-categoria h3 {
    font-size: 1.3em;
  }
}

/* Celulares 375px - 424px */
@media (min-width: 375px) and (max-width: 425px) {
  .skills-contenedor {
    padding: 1rem;
  }

  .skills {
    gap: 0.6rem;
    justify-content: center;
  }

  .skill {
    flex: 1 1 calc(48% - 0.6rem); /* 2 tarjetas por fila */
    max-width: none;
    min-width: 0;
    padding: 0.5em 0.3em;
    gap: 6px;
  }

  .skill img {
    width: 26px;
    height: 26px;
  }

  .skill span {
    font-size: 0.75em;
    line-height: 1.2;
  }

  .skills-categoria h3 {
    font-size: 1.2em;
    margin-bottom: 0.8rem;
  }

  .skills-categoria {
    margin-bottom: 1.5rem;
  }
}

/* Celulares pequeños (menos de 375px) */
@media (max-width: 374px) {
  .skills-contenedor {
    padding: 0.8rem;
  }

  .skills {
    gap: 0.5rem;
  }

  .skill {
    flex: 1 1 calc(48% - 0.5rem);
    padding: 0.4em 0.2em;
    gap: 5px;
  }

  .skill img {
    width: 24px;
    height: 24px;
  }

  .skill span {
    font-size: 0.7em;
  }

  .skills-categoria h3 {
    font-size: 1.1em;
  }
}

/* Computadoras */
@media (min-width: 1024px) {
  .skills {
    gap: 1.5rem;
  }

  .skill {
    flex: 1 1 calc(20% - 1.5rem);
  }
}
</style>