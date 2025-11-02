<template>
    <nav class="navbar">
      <div class="navbar-menu">
        <ul>
          <a v-for="nav in navegacion" :key="nav.nombre" :href="nav.enlace" class="nav-item" >{{ nav.nombre }}</a>

        </ul>

      </div>
    </nav>
</template>
<script setup>
import { ref } from 'vue';
const navegacion= ref([
    {id:1, nombre: 'Integrantes', enlace: '#integrantes'},
    {id:2, nombre: 'Proyectos', enlace: '#proyectos'},
    {id:3, nombre: 'Habilidades', enlace: '#habilidades'},
]);

</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  max-width: 1135px;
  width: 90%;
  

  background-color: rgba(0, 50, 0, 0.5);
  
  color: #fff;
  padding: 0.5rem 1rem;
  align-items: center;
  z-index: 100;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  border-radius: 0 0 10px 10px;
}

.navbar-item {
  color: #fff;
  text-decoration: none;
  margin-right: 1rem;
}

.navbar-menu {
  display: flex;
  justify-content: flex-end;
}

.nav-list {
  list-style: none;
}

a {
  border: 1px solid;
  border-color: hsla(160, 100%, 37%, 0.2);
  border-radius: 5px;
  text-decoration: none;
  transition: 0.4s;
  padding: 5px;
}

a:hover {
  background-color: hsl(27, 93%, 47%);
}

@media (max-width: 768px) {
  .navbar {
    width: 95%;
  }
  
  .navbar-menu {
    display: flex;
    justify-content: flex-end;
    width: 100%;
  }
}
</style>