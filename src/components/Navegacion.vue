<script setup>
import UserActions from './UserActions.vue'
</script>

<template>
  <header class="main-header">
    <div class="logo">
      <a href="index.html"><img src="../assets/PRUEBA.PNG" alt="Logo de la tienda" class="logo-image"></a>
    </div>
    <nav class="top-nav">
      <ul class="menu">
        <li class="menu-item">
          <a href="#" class="menu-link">Boxers de Hombre</a>
        </li>
        <li class="menu-item">
          <a href="#" class="menu-link">Brasier</a>
        </li>
        <li class="menu-item">
          <a href="#" class="menu-link">Conjuntos</a>
        </li>
        <li class="menu-item">
          <a href="#" class="menu-link">Tríos de Calzones</a>
        </li>
      </ul>
    </nav>
    <UserActions></UserActions>
  </header>
</template>

<style scoped>
.main-header {
    align-items: center;
    background: #ffefcd;
    color: #1D1D1B;
    display: flex;
    justify-content: space-between;
    padding: .3125rem 5rem;
    position: sticky;
    right: 0px;
    top: 0px;
    width: 100%;
}

.logo-image {
    height: auto;
    width: 9.375rem;
}
.logo-image:hover {
    transform: scale(1.03);
    transition-duration: 0.2s;
}


.menu {
    align-items: center;
    display: flex;
    justify-content: space-between;
    list-style: none;
}

.menu-item {
    transition: all .3s ease-out;
}

.menu-item:hover {
    transform: scale(1.2);
    transition: .3s;
}

.menu-link {
    color: #1D1D1B;
    height: 100%;
    opacity: 0.75;
    padding: 1.625rem 1.375rem;
    text-decoration: none;
    transition: all .1s ease-out;
}

.menu-link:hover {
    opacity: 1;
}
</style>
