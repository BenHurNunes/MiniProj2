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
        <h2 class="title">Patrocinador</h2>
        <div class="buttons">
          <router-link to="/">
            <button>Home</button>
          </router-link>
          <router-link to="/novos-patrocinadores">
            <button>Novo Patrocinador</button>
          </router-link>
        </div>
        <table>
          <thead>
            <tr>
              <th>Nome</th>
              <th>Animal</th>
              <th>Perfil</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(patrocinador, index) in patrocinadores" :key="index">
              <td>{{ patrocinador.nome }}</td>
              <td>{{ patrocinador.animal }}</td>
              <td class="action-buttons">
                <button @click="verInfo(patrocinador)">Info</button>
                <button @click="editarPatrocinador(patrocinador)">Editar</button>
                <button @click="deletarPatrocinador(patrocinador)">Deletar</button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
  
      <footer>
        <p>&copy; 2023 Animalec. Todos os direitos reservados.</p>
      </footer>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Patrocinadores',
    data() {
      return {
        patrocinadores: [
          { nome: 'Empresa A', animal: 'Leão' },
          { nome: 'Empresa B', animal: 'Elefante' },
          { nome: 'Empresa C', animal: 'Girafa' },
        ],
      };
    },
    methods: {
      verInfo(patrocinador) {
        alert(`Informações sobre ${patrocinador.nome}`);
      },
      editarPatrocinador(patrocinador) {
        alert(`Editar ${patrocinador.nome}`);
      },
      deletarPatrocinador(patrocinador) {
        if (confirm(`Tem certeza que deseja deletar ${patrocinador.nome}?`)) {
          this.patrocinadores = this.patrocinadores.filter(
            (p) => p.nome !== patrocinador.nome
          );
        }
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
    margin-top: 20px;
  }
  
  .title {
    text-align: center;
    margin-bottom: 20px;
    font-size: 24px;
    font-weight: bold;
  }
  
  .buttons {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-bottom: 20px;
  }
  
  .buttons button {
    background-color: #a7fba1;
    border: none;
    padding: 10px 20px;
    border-radius: 20px;
    font-size: 16px;
    cursor: pointer;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .buttons button:hover {
    background-color: #94e18e;
  }
  
  table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 20px;
  }
  
  th,
  td {
    padding: 10px;
    text-align: center;
    border: 1px solid #a7fba1;
  }
  
  th {
    background-color: #a7fba1;
    font-weight: bold;
  }
  
  tr:nth-child(even) {
    background-color: #f0fff0;
  }
  
  .action-buttons button {
    background-color: #a7fba1;
    border: none;
    padding: 5px 10px;
    border-radius: 10px;
    font-size: 14px;
    cursor: pointer;
  }
  
  .action-buttons button:hover {
    background-color: #94e18e;
  }
  
  footer {
    background-color: #1a4517;
    color: white;
    text-align: center;
    width: 100%;
    padding: 10px;
  }
  
  footer p {
    font-size: 12px;
  }
  </style>