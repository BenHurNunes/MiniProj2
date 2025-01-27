<template>
    <div>
      <header>
        <div class="logo">
          <img src="@/assets/noun-animals-13643.png" alt="Logo Animalec" />
          <h1>Animalec</h1>
        </div>
        <nav>
          <router-link to="/">Animais</router-link>
          <router-link to="/">Quizzes</router-link>
          <router-link to="/">Contato</router-link>
          <router-link to="/admin">Admin</router-link>
        </nav>
      </header>
  
      <div class="container">
        <h2 class="title">Novo Patrocinador</h2>
        <form class="form">
          <div class="form-row">
            <input type="text" placeholder="Inserir nome" v-model="novoPatrocinador.nome" />
            <input type="text" placeholder="Inserir animal" v-model="novoPatrocinador.animal" />
          </div>
          <div class="buttons">
            <button type="button" @click="salvarPatrocinador">Salvar</button>
            <button type="button" @click="limparFormulario">Excluir</button>
          </div>
        </form>
      </div>
  
      <footer>
        <p>&copy; 2023 Animalec. Todos os direitos reservados.</p>
      </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: 'NovosPatrocinadores',
    data() {
      return {
        novoPatrocinador: {
          nome: '',
          animal: '',
        },
      };
    },
    methods: {
      salvarPatrocinador() {
        if (this.novoPatrocinador.nome && this.novoPatrocinador.animal) {
          alert(`Patrocinador salvo: ${this.novoPatrocinador.nome} - ${this.novoPatrocinador.animal}`);
          // Aqui você pode adicionar a lógica para salvar no backend
          this.limparFormulario();
        } else {
          alert('Por favor, preencha todos os campos.');
        }
      },
      limparFormulario() {
        this.novoPatrocinador.nome = '';
        this.novoPatrocinador.animal = '';
      },
    },
  };
  </script>
  
  <style scoped>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    min-height: 100vh;
    background-color: #fff;
  }
  
  header {
    display: flex;
    justify-content: space-between;
    width: 90%;
    align-items: center;
    margin: 20px auto;
  }
  
  header .logo {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  
  header .logo img {
    width: 50px;
    height: auto;
  }
  
  nav {
    font-size: 16px;
  }
  
  nav a {
    text-decoration: none;
    color: black;
    margin: 0 10px;
  }
  
  .container {
    width: 90%;
    max-width: 1200px;
    margin-top: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .title {
    text-align: center;
    margin-bottom: 30px;
    font-size: 24px;
    font-weight: bold;
  }
  
  .form {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
  
  .form-row {
    display: flex;
    gap: 20px;
  }
  
  .form-row input {
    padding: 10px;
    font-size: 16px;
    border: 2px solid #a7fba1;
    border-radius: 10px;
    outline: none;
    text-align: center;
    width: 200px;
  }
  
  .form-row input:focus {
    border-color: #94e18e;
  }
  
  .buttons {
    display: flex;
    gap: 20px;
  }
  
  .buttons button {
    background-color: #a7fba1;
    border: none;
    padding: 10px 20px;
    border-radius: 10px;
    font-size: 16px;
    cursor: pointer;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .buttons button:hover {
    background-color: #94e18e;
  }
  
  footer {
    background-color: #1a4517;
    color: white;
    text-align: center;
    width: 100%;
    padding: 10px;
    margin-top: auto;
  }
  
  footer p {
    font-size: 12px;
  }
  </style>