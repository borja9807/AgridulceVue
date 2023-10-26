<template>
  <footer class="footer">
    <div class="newsletter">
      <h2>Suscríbete a nuestro boletín</h2>
      <form @submit.prevent="subscribe">
        <input type="email" v-model="email" placeholder="Correo Electrónico" required>
        <button type="submit">Suscribir</button>
      </form>
    </div>
    <div class="social-links">

      <a href="https://www.facebook.com/tupagina" class='social-button' target="_blank"><i
          class="fa-brands fa-facebook fa-xl"></i></a>
      <a href="https://www.instagram.com/tupagina" class='social-button' target="_blank"><i
          class="fa-brands fa-instagram fa-xl" style="color: #ffffff;"></i></a>
      <a href="https://www.tiktok.com/@tupagina" class='social-button' target="_blank"><i
          class="fa-brands fa-tiktok fa-lg" style="color: #ffffff;"></i></a>
      <a href="https://api.whatsapp.com/send?phone=3218967984" class='social-button' target="_blank"><i
          class="fa-brands fa-whatsapp fa-xl" style="color: #009e0b;"></i></a>
    </div>
    <div class="contact-info">
      <h2>Contacto</h2>
      <p>agridulce@agridulce.com</p>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      email: ''
    };
  },
  methods: {
    subscribe() {
      // Aquí puedes enviar el correo electrónico a tu servidor o realizar otras acciones, por ejemplo, mostrar un mensaje de confirmación.
      console.log('Correo electrónico a suscribir:', this.email);
    }
  }
};
</script>

<style scoped>
.footer {
  background-color: rgb(129, 129, 129);
  color: #fff;
  padding: 1rem;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
}

.social-links {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  margin-top: 1.5rem;
}

.social-button {
  margin: 0 0.7rem;
  text-decoration: none;
  color: #0077B5;
}

.social-button:hover {
  transform: scale(1.1);
  transition: .1s;
}

.contact-info {
  text-align: center;
  margin-top: 1rem;
  color: #fff;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  font-size: medium;

}

.newsletter {
  text-align: center;
  margin-top: 2rem;
}

.newsletter h2 {
  margin-bottom: 1rem;
  color: #fff;
  font-size: large;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.newsletter input {
  padding: 0.5rem;
  margin-right: 0.5rem;
  border-radius: 0.5rem;
  padding: 1 2rem;
  outline: none;
  border: 0.1rem solid gray;
  width: 16rem;
}

.newsletter button {
  background-color: #ad6565;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 0.5rem;
}

.newsletter button:hover {
  transform: scale(1.03);
  transition: .1s;
}
</style>