<script setup lang="ts">
import emailjs from 'emailjs-com';
import { ref } from 'vue';

const name = ref('');
const email = ref('');
const message = ref('');

const publicKey = import.meta.env.VITE_PUBLIC_KEY;
const templateId = import.meta.env.VITE_TEMPLATE_ID;
const serviceId = import.meta.env.VITE_SERVICE_ID;

const sendEmail = async (e: Event) => {
  e.preventDefault(); // Evitar recarga de la página

  if (!name.value || !email.value || !message.value) {
    alert('Por favor, completa todos los campos.');
    return;
  }

  try {
    console.log('Public Key:', publicKey);
console.log('Template ID:', templateId);
console.log('Service ID:', serviceId);

    await emailjs.send(
      serviceId, // Reemplaza con tu ID de servicio
      templateId, // Reemplaza con tu ID de plantilla
      {
        name: name.value,
        email: email.value,
        message: message.value,
      },
      publicKey // Reemplaza con tu ID de usuario de EmailJS
    );

    alert('Correo enviado con éxito.');
    name.value = '';
    email.value = '';
    message.value = '';
  } catch (error) {
    console.error('Error al enviar el correo:', error);
    alert('Ocurrió un error al enviar el correo. Inténtalo nuevamente.');
  }
};
</script>

<template>
  <div class="container">
    <form @submit="sendEmail">
      <label for="name">Name</label>
      <input
        id="name"
        type="text"
        v-model="name"
        name="name"
        placeholder="Your Name"
      >
      <label for="email">Email</label>
      <input
        id="email"
        type="email"
        v-model="email"
        name="email"
        placeholder="Your Email"
      >
      <label for="message">Message</label>
      <textarea
        id="message"
        name="message"
        v-model="message"
        cols="30"
        rows="5"
        placeholder="Message"
      ></textarea>
      <input type="submit" value="Send">
    </form>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.container {
  display: block;
  margin: auto;
  text-align: center;
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
  width: 50%;
}

label {
  float: left;
}

input[type=text],
input[type=email],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type=submit] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #45a049;
}
</style>
