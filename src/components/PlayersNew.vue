<script>
export default {
  data: function () {
    return {
      newPlayerParams: {},
    };
  },
  methods: {
    handleSubmit: function () {
      this.$emit("createPlayer", this.newPlayerParams);
      this.newPlayerParams = {};
    },
  },
};
</script>


<template>
  <div>
    <h1>New Player</h1>
    <form v-on:submit.prevent="handleSubmit">
      <div>
        Name:
        <input type="text" v-model="newPlayerParams.name" />
      </div>
      <div>
        Position:
        <input type="text" v-model="newPlayerParams.position" />
      </div>
      <div>
        Nationality:
        <input type="text" v-model="newPlayerParams.nationality" />
      </div>
      <div>
        Dob:
        <input type="text" v-model="newPlayerParams.dob" />
      </div>
      <button type="submit">Create player</button>
    </form>
  </div>
</template>

<style></style>