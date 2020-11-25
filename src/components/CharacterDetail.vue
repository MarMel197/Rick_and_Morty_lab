<template>
    <div v-if="character">
    <h3>{{character.name}}</h3>
    <p>Species: {{character.species}}</p>
    <p>Status : {{character.status}}</p>
    <p>Gender : {{character.gender}}</p>
    <p>Picture: {{character.image}}</p>
    </div>
    <div v-else>
        <p>Please choose a character</p>
    </div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
}
</script>

<style>

</style>