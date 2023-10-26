<template>
  <div class="user-actions">
    <div class="search-bar">
      <i class="srcbtn fa-solid fa-magnifying-glass fa-lg" @click="toggleSearchBar"></i>
      <form id="search-form" :class="searchBarClass">
        <input type="text" class="search-bar-input" placeholder="Buscar productos">
        <button class="search-bar-btn">Buscar</button>
      </form>
    </div>

    <Cart></Cart>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isSearchBarVisible: false
    };
  },
  computed: {
    searchBarClass() {
      return {
        'show-bar': this.isSearchBarVisible,
        'hide-bar': !this.isSearchBarVisible
      };
    }
  },
  methods: {
    toggleSearchBar() {
      this.isSearchBarVisible = !this.isSearchBarVisible;
    }
  },
  components: { Cart }
};
import Cart from './Cart.vue';
</script>

<style scoped>
.user-actions {
  display: flex;
  gap: .9375rem;
  justify-content: center;
  align-items: center;
}

.search-bar {
  gap: .5rem;
  overflow: hidden;
  padding-left: 5px;
  align-items: center;
  color: #1D1D1B;
  display: flex;
  justify-content: center;
  text-decoration: none;


}

.srcbtn:hover {
  transform: scale(1.1);
  transition: .1s;
  cursor: pointer;
}

.search-bar-icon {
  cursor: pointer;
  opacity: 0.75;
  transition: all .25s ease-out;
}

.search-bar-input {
  border: 2px solid #949292;
  border-radius: .375rem;
  font-family: serif;
  font-size: 1rem;
  padding: .5rem;
  transition: all .1s ease-out;
}

.search-bar-input:focus {
  border-color: #ad6565;
}

.search-bar-btn {
  all: unset;
  background: #ad6565;
  border: 2px solid #ad6565;
  border-radius: .375rem;
  color: #fff;
  cursor: pointer;
  font-family: system-ui;
  font-size: 1rem;
  font-weight: 500;
  padding: 8px;
  transition: all .3s ease-out;
}

.search-bar-btn:hover,
.search-bar-btn:focus {
  background: #fff;
  color: #ad6565;
}

.hidden {
  display: none;
}

.hide-bar {
  margin-right: -290px;
  transition: all .3s ease-in-out;
}

.show-bar {
  margin-right: 0px;
  transition: all .3s ease-in-out;
}
</style>

