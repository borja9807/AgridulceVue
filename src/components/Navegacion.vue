<script setup>
import UserActions from './UserActions.vue'
</script>

<template>
  <header class="main-header">
    <div class="logo">
      <a href="index.html"><img src="../assets/PRUEBA.PNG" alt="Logo de la tienda" class="logo-image"></a>
    </div>
    <div class="menu-container">
      <nav class="top-nav">
        <ul class="menu" :class="{ 'menu-open': isMenuOpen }">
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
      <div class="menu-icon" @click="toggleMenu">
        <i class="fa-solid fa-bars"></i>
      </div>
    </div>
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

.logo {
  display: flex;
  align-items: center;
}

.logo-image {
  height: auto;
  width: 9.375rem;
  transition: transform 0.2s;
}

.menu-container {
  display: flex;
  align-items: center;
}

.menu {
  display: flex;
  list-style: none;
  align-items: center;
}

.menu-icon {
  display: none;
  font-size: 1.5rem;
  cursor: pointer;
}

.menu-open {
  display: flex;
  flex-direction: column;
}

.menu-item {
  transition: all .3s ease-out;
  text-align: center;
}

.menu-link {
  color: #1D1D1B;
  height: 100%;
  opacity: 0.75;
  padding: 1.625rem 1.375rem;
  text-decoration: none;
  transition: all .1s ease-out;
}

.menu-item:hover {
  transform: scale(1.2);
}

.menu-link:hover {
  opacity: 1;
}

@media (max-width: 900px) {
  .menu {
    display: none;
    flex-direction: column;
    padding: 1rem;
  }

  .menu-icon {
    display: block;
  }
}
</style>

<script>
import { ref } from 'vue';

export default {
  components: {
    UserActions,
  },
  setup() {
    const isMenuOpen = ref(false);

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    return {
      isMenuOpen,
      toggleMenu,
    };
  },
};
</script>