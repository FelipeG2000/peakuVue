<template>
    <nav class="navbar shadow px-2 py-3 border-bottom navbar-light bg-light navbar-expand-lg">
      <img height="60" src="../assets/logo-blue.png">
      <div class="order-4 order-md-1 navbar-collapse collapse" style="display: none;">
        <ul class="navbar-nav ml-md-auto align-items-md-center d-flex">
          <li v-for="link in navLinks" :key="link.id" class="nav-item">
            <a :href="link.url" class="nav-link" :class="{ 'active': link.active }">{{ link.text }}</a>
          </li>
        </ul>
      </div>
    </nav>
  </template>
  
  <script lang="ts" setup>
  import {ref,Ref} from 'vue'
  interface NavLink {
  id: number;
  url: string;
  text: string;
  active: boolean;
}
  const navLinks:Ref<Array<NavLink>> = ref([
    { id: 1, url: 'https://peaku.io/es/empleos', text: 'Empleos', active: true },
    { id: 2, url: 'https://peaku.io/es/bootcamp-fullstack', text: 'Bootcamp', active: false },
    { id: 3, url: 'https://peaku.io/es/sobre-nosotros', text: 'Sobre nosotros', active: false },
    { id: 4, url: 'https://peaku.io/es/profesionales', text: 'Para profesionales', active: false },
    { id: 5, url: 'https://peaku.io/es/empresas', text: 'Para empresas', active: false },
  ]);
  </script>

  <style scoped>
  .navbar {
    padding: 20px; 
  }
  
  .navbar-nav {
    display: flex;
    flex-direction: row;
    justify-content: flex-end; 
    padding-left: 0;
    margin-bottom: 0;
    list-style: none;
  }
  
  .navbar-light .navbar-nav .nav-link {
    color: rgba(0, 0, 0, .7);
    font-size: 20px; 
  }
  
  .nav-link {
    display: block;
    padding: 0.5rem 1rem;
  }
  </style>
  