<template>
  <div class="movie-card">
    <h3>{{ filme.titulo }}</h3>
    <p class="director">Diretor: {{ filme.diretor }}</p>
    <p class="year">Ano do filme: {{ filme.ano }}</p>
    <button>Editar</button>
    <button>Deletar</button>
  </div>
</template>

<script setup>
const props = defineProps(["filme"]);
</script>

<style scoped>
.movie-card {
  background: #2c2c2c;
  padding: 15px;
  border-radius: 8px;
  border: 1px solid #444;
}
.movie-card h3 {
  color: #e74c3c;
  margin-bottom: 5px;
}
.director {
  font-size: 1em;
  color: #aaa;
}
.year {
  font-size: 0.9em;
  color: #888;
}
</style>