<template>
  <div class="container">
    <header>
      <h1>🎬 Meu Catálogo de Filmes</h1>
    </header>

    <main class="movie-list">
        <FilmeCard 
        v-for="filme in filmes" 
        :key="filme.id" 
        :filme="filme" />
    </main>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import FilmeCard from './components/FilmeCard.vue';

const filmes = ref([]);

 function carregarFilmes() {
  filmes.value = [
  { id: 1, titulo: 'Interestelar', diretor: 'Christopher Nolan', ano: 2014 },
  { id: 2, titulo: 'Parasita', diretor: 'Bong Joon Ho', ano: 2019 },
  { id: 3, titulo: 'Cidade de Deus', diretor: 'Fernando Meirelles', ano: 2002 },
  { id: 4, titulo: 'O Poderoso Chefão', diretor: 'Francis Ford Coppola', ano: 1972 }
];
}

onMounted(() => {
  carregarFilmes();
});

</script>

<style>
/* Estilos globais para a aplicação */
* {
  box-sizing: border-box;
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
}
body {
  background-color: #1a1a1a;
  color: #f0f0f0;
}
.container {
  max-width: 900px;
  margin: 40px auto;
  padding: 20px;
}
header h1 {
  text-align: center;
  color: #e74c3c;
  margin-bottom: 30px;
}
.movie-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}
</style>