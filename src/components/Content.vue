<script>
import axios from "axios";
import PlayersIndex from "./PlayersIndex.vue";
import PlayersNew from "./PlayersNew.vue";

  export default {
    components: {
      PlayersIndex,
      PlayersNew,
    },
    data: function () {
      return {
        players: [],
      };
    },
    created: function () {
      this.handleIndexPlayers();
    },
    methods: {
      handleIndexPlayers: function () {
        axios.get("http://localhost:3000/players.json").then((response) => {
          console.log("players index", response);
          this.players = response.data;
        });
      },
      
      handleCreatePlayer: function (params) {
        axios
          .post("http://localhost:3000/players.json", params)
          .then((response) => {
            console.log("players create", response);
            this.players.push(response.data);
          })
          .catch((error) => {
            console.log("players create error", error.response);
          });
      },

    },
  };
  </script>

  <template>
    <main>
      <PlayersNew v-on:createPlayer="handleCreatePlayer" />
      <PlayersIndex v-bind:players="players" />
    </main>
  </template>

  <style></style>