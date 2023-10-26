<template>
  <div class="product-container">
    <div class="product" v-for="product in products" :key="product.id">
      <img :src="product.image" :alt="product.title" class="product-image">
      <h2 class="product-title">{{ product.title }}</h2>
      <p class="product-description">{{ product.description }}</p>
      <p class="product-price">Precio: ${{ product.price }}</p>
      <div>
        <label :for="'size-' + product.id">Talla:</label>
        <select :id="'size-' + product.id">
          <option value="Selecciona una talla"></option>
          <option value="S">S</option>
          <option value="M">M</option>
          <option value="L">L</option>
          <option value="XL">XL</option>
        </select>
      </div>
      <p :id="'available-quantity-' + product.id">Cantidad Disponible: {{ product.quantity }}</p>
      <button class="add-to-cart-btn" @click="addToCart(product.id)">Agregar al Carrito</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          id: 1,
          title: 'Lebron loco',
          description: 'Descripción del producto 1.',
          price: 19.99,
          image: '.assets/img/foto_no_exif (2).jpg',
          quantity: 10

        },
        // Agrega más productos aquí
      ]
    };
  },
  methods: {
    addToCart(productId) {
      // Agregar lógica para agregar el producto al carrito
      // Puedes usar VueX o emitir eventos personalizados para manejar esto.
    }
  }
};

</script>

<style scoped>
.product-container {
  display: flex;
  flex-wrap: wrap;
  gap: 1.25rem;
  

  /* Espacio entre los productos */
}

.product {
  max-width: 20rem;
  /* Ancho máximo de cada producto */
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-align: center;
  position: relative;
}

.product-image {
  max-width: 100%;
}


</style>
