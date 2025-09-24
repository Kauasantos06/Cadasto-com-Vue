<script setup>
import { ref } from 'vue';

// Define reactive variables for form inputs
const nome = ref('');
const fone = ref('');
const email = ref('');
const cpf = ref('');

// Method to handle form submission
const check = () => {
  // Access the values using .value
  console.log('Nome:', nome.value);
  console.log('Fone:', fone.value);
  console.log('Email:', email.value);
  console.log('CPF:', cpf.value);

  // Add your form validation logic here
  if (nome.value && fone.value && email.value && cpf.value) {
    alert('Formulário enviado com sucesso!');
  } else {
    alert('Por favor, preencha todos os campos.');
  }
};
</script>

<template>
  <div class="container">
    <form @submit.prevent="check()">
      <h2>Cadastre-se</h2>
      <br />
      <div class="blocoInput">
        <label for="nome">Nome</label>
        <input type="text" id="nome" class="form-input" v-model="nome" /><br />
      </div>
      <div class="blocoInput">
        <label for="fone">Fone</label>
        <input type="tel" id="fone" class="form-input" v-model="fone" /><br />
      </div>
      <div class="blocoInput">
        <label for="email">Email</label>
        <input type="email" id="email" class="form-input" v-model="email" /><br />
      </div>
      <div class="blocoInput">
        <label for="cpf">CPF</label>
        <input type="text" id="cpf" class="form-input" v-model="cpf" /><br />
      </div>
      <button type="submit" class="btn">Login</button>
    </form>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  font-family: Arial, sans-serif;
  background-color: #f0f2f5;
}

form {
  display: flex;
  flex-direction: column;
  background: #fff;
  padding: 40px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
  text-align: center;
}

h2 {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333;
}

.blocoInput {
  margin-bottom: 20px;
  text-align: left;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
  color: #555;
}

.form-input {
  width: 100%;
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 4px;
  box-sizing: border-box;
  font-size: 16px;
  transition: border-color 0.3s;
}

.form-input:focus {
  border-color: #007bff;
  outline: none;
}

.btn {
  width: 100%;
  padding: 12px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  font-size: 18px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
}

.btn:hover {
  background-color: #0056b3;
  transform: translateY(-2px);
}
</style>
