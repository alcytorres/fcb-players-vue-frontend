<script>
export default {
  props: {
    players: Array,
  },
};
</script>

<template>
  <div>
    <h1>All players</h1>
    <div v-for="player in players" v-bind:key="player.id">
      <h2>{{ player.name }}</h2>
      <p>Position: {{ player.position }}</p>
      <p>Nationality: {{ player.nationality }}</p>
      <p>Dob: {{ player.dob }}</p>
    </div>
  </div>
</template>

<style></style>