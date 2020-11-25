<template>
  <div>
    <h1>Rick & Morty</h1>
    <characters-list :characters='characters'></characters-list>
    <character-detail :character='selectedCharacter'></character-detail>
    <!-- <label for="character_select">Select a Character:</label>
    <option disable value="">Select a Character</option>
    <option v-for="character in characters" :key="character.id" :value="character">{{chratacter.name}}</option>
  <select name="" id=""></select> -->
  </div>
</template>

<script>

import CharactersList from './components/CharactersList.vue';
import CharacterDetail from './components/CharacterDetail.vue'
import {eventBus} from './main.js'

export default {
  name: 'app',
  data(){
    return {
      characters: [],

      selectedCharacter: null
      
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character')
    .then(response => response.json())
    .then(data => this.characters = data.results)
    
    
    eventBus.$on('character-selected', (character) => {
    this.selectedCharacter = character;
    })

  },

  components: {
    // Turns import into HTML to be used at top
    "characters-list": CharactersList,
    "character-detail": CharacterDetail

  }
}
</script>

<style>

</style>
