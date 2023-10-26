<template>
  <div>
    <i class="cart fa-solid fa-cart-shopping fa-lg" @click="openCart"></i>
    <div class="modal" :class="{ active: cartActive }">
      <div class="modal-container">
        <!-- Contenido del carrito -->
        <div id="cart-content" class="modal-content cart-visible">
          <header class="cart-header">
            <h2>Carrito</h2>
          </header>
          <section class="cart-body">
            <ul id="cart-items">
              <!-- Los elementos del carrito se mostrarán aquí -->
            </ul>
          </section>
          <footer class="cart-footer">
            <div class="cart-list-price">
              <ul>
                <li>Subtotal: <strong>$0.00</strong></li>
                <li>Descuento: <strong>$0.00</strong></li>
              </ul>
              <h4 class="modal-cart-total">Total: <span id="cart-total">$0.00</span></h4>
            </div>
            <div class="modal-btns">
              <button @click="closeCart" class="btn close-btn">Cerrar Carrito</button>
              <a href="#" class="btn">Comprar ahora</a>
            </div>
          </footer>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  data() {
    return {
      cartActive: false
    };
  },
  methods: {
    openCart() {
      this.cartActive = true;
    },
    closeCart() {
      this.cartActive = false;
    }
  }
};
</script>
  
<style scoped>
.cart:hover {
  transform: scale(1.1);
  transition: .3s;
}

a:link,
a:visited,
a:active {
  text-decoration: none;
}

#cart-button {
  color: #1D1D1B;
}

.cart {
  align-items: center;
  color: #1D1D1B;
  display: flex;
  justify-content: center;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.75;
  transition: all .25s ease-out;
}

.modal {
  background-color: #fff;
  height: 100vh;
  max-width: 300px;
  opacity: 0;
  position: fixed;
  right: 0;
  top: 0;
  transform: translateX(100%);
  transition: all 0.2s ease-in;
  visibility: hidden;
  width: 100%;
  z-index: 20000;
}

.modal::after {
  background-color: rgba(0, 0, 0, 0.6);
  content: '';
  height: 100vh;
  opacity: 0;
  pointer-events: none;
  position: fixed;
  right: 300px;
  top: 0;
  transition: all .2s ease-in;
  width: 100vw;
  z-index: 999;
}

.modal.active {
  opacity: 1;
  transform: none;
  visibility: visible;
}

.modal.active::after {
  opacity: 1;
  pointer-events: auto;
}

.modal-container {
  height: 100%;
  padding: 2rem;
  position: relative;
  z-index: 1000;
}

.modal-content {
  display: flex;
  flex-flow: column;
  height: 100%;
  overflow: hidden;
}

.cart-header {
  border-bottom: 1px solid #dbdbdb;
  margin-bottom: 30px;
  padding-bottom: 30px;
}

.cart-header h2 {
  color: #ad6565;
  font-size: 1.5rem;
  text-align: center;
}

.cart-body {
  flex-grow: 1;
  overflow-x: hidden;
  overflow-y: visible;
  position: relative;
  width: 100%;
}

.cart-footer {
  border-top: 1px solid #dbdbdb;
  margin-top: 30px;
  padding-top: 30px;
}

.cart-list-price ul li+li {
  margin-top: 10px;
}

.cart-list-price ul li strong {
  color: #ad6565;
}

.modal-cart-total {
  color: #ad6565;
  font-size: 1.25rem;
  margin: 20px 0;
}

.modal-btns {
  border-top: 1px solid #dbdbdb;
  display: flex;
  flex-direction: column;
  gap: 6px;
  justify-content: space-between;
  padding-top: 30px;
}

.btn {
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
  text-align: center;
  transition: all .2s ease;
}

.btn:hover {
  background: #fff;
  border: 2px solid #ad6565;
  color: #ad6565;
}

.close-btn {
  background: #fff;
  color: #ad6565;
}

.close-btn:hover {
  background: #ad6565;
  color: #fff;
}
</style>