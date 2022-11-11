<template>
  <div>
    <input type="text" id="name" placeholder="Utilisateur"/>
    <input type="text" id="pass" placeholder="Mot de passe" @input="testLogin" v-model="password"/>
    <p id="message">{{ message }}</p>
  </div>
</template>

<script setup>
import {ref} from "vue";

let message = ref('');
let password = ref('');

function testLogin() {
  if (password.value.match(/[0-9]/g) &&
      password.value.match(/[a-z]/g) &&
      password.value.match(/[A-Z]/g) &&
      password.value.length >= 8
  ) {
    message.value = "Mot de passe correct";
    document.getElementById('message').style.color = 'green';
  } else {
    message.value = "Mot de passe incorrect";
    document.getElementById('message').style.color = 'red';
  }
}
</script>

<style scoped>

</style>
