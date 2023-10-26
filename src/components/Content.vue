<template>
    <div>
      <div class="content" :class="{ 'mobile': isMobile, 'tablet': isTablet, 'desktop': isDesktop }">
        <Navegacion></Navegacion>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isMobile: false,
        isTablet: false,
        isDesktop: false,
      };
    },
    created() {
      this.checkWindowSize();
      window.addEventListener('resize', this.checkWindowSize);
    },
    destroyed() {
      window.removeEventListener('resize', this.checkWindowSize);
    },
    methods: {
      checkWindowSize() {
        const windowWidth = window.innerWidth;
        this.isMobile = windowWidth <= 768;
        this.isTablet = windowWidth > 768 && windowWidth <= 1024;
        this.isDesktop = windowWidth > 1024;
      },
    },
  };
  import Navegacion from './Navegacion.vue';
  </script>
  