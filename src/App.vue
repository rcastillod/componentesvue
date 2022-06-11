<template>
  <div id="app">
    <div class="main-wrapper">
      <div class="personajes">
        <personaje 
          v-for="personaje in personajes" 
          :key="personaje.id"
          :id="personaje.id"
          :name="personaje.name"
          :status="personaje.status"
          :species="personaje.species"
          :imageSrc="personaje.imageSrc"
        ></personaje>
      </div>
    </div>
  </div>
</template>

<script>
import Personaje from '@/components/PersonajeCard.vue'

export default {
  name: 'App',
  components: {
    'personaje': Personaje
  },
  data: function() {
    return {
      personajes: [
        { id: 1, name: "Rick Sanchez", status: "Alive", species: "Human", imageSrc: "https://rickandmortyapi.com/api/character/avatar/1.jpeg" },
        { id: 2, name: "Morty Smith", status: "Alive", species: "Human", imageSrc: "https://rickandmortyapi.com/api/character/avatar/2.jpeg" },
        { id: 3, name: "Summer Smith", status: "Alive", species: "Human", imageSrc: "https://rickandmortyapi.com/api/character/avatar/3.jpeg" },
        { id: 4, name: "Beth Smith", status: "Alive", species: "Human", imageSrc: "https://rickandmortyapi.com/api/character/avatar/4.jpeg" }
      ]
    }
  }
}
</script>

<style>
:root {
  --clr-card-bg: 60 69% 62%;
  --clr-white: 0 0% 100%;
}
body {
  background-image: url('assets/rm-bg.png');
  background-size: cover;
  background-position: center bottom;
  background-repeat: no-repeat;
  display: grid;
  height: 100vh;
  place-items: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
}
.main-wrapper {
  margin-inline: auto;
  width: min(100% - 2rem, 68.75rem);
}
.personajes {
  display: grid;
  column-gap: 1.875rem;
  row-gap: 6.25rem;
  grid-template-columns: repeat(auto-fit, minmax(13.4375rem, 1fr));
}
</style>
