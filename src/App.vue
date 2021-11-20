<template>
  <div id="app">
    <div class="card text-center m-3">
    <h5 class="card-header">Games List</h5>
            <table class="table">
              <thead>
                <tr>
                  <th scope="col">#</th>
                  <th scope="col" class="text-end pe-5">Guessing Score</th>
                </tr>
              </thead>
            <tr v-for='(game, index) in games' :key="index">
                <td>{{ index + 1}}</td>
                <td>
                    <table class="table table-borderless">
                        <tr>
                            <td>Home</td>
                            <td>{{ game.home_team.name }}</td>
                            <td>{{ game.home_team.guessing_score }}</td>
                        </tr>
                        <tr>
                            <td>Away</td>
                            <td>{{ game.away_team.name }}</td>
                            <td>{{ game.away_team.guessing_score }}</td>
                        </tr>
                    </table>
                </td>
            </tr>
        </table>
  </div>
  <!-- <div v-for="(player, index) in players" :key="index">
    {{ player.home_team.players }}
  </div> -->

    <!-- <player-list :player="playerList" /> -->
    <!-- <div class="card text-center m-3">
    <h5 class="card-header">Players List</h5>
           <div class="row">
    <div class="col-6">
        <table class="table">
            <thead>
              <tr>
                <th scope="col">#</th>
                <th scope="col">Name</th>
                <th scope="col">G-score</th>
                <th scope="col">Boost</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for='(player, index) in players' :key="index">
                <th scope="row">{{ index + 1}}</th>
                <td>{{ player.home_team.players.player_name }}</td>
                <td>{{ player.home_team.players.guessing_score.score }}</td>
                <td>{{ player.home_team.players.guessing_score.boost }}</td>
              </tr>
            </tbody>
          </table>
    </div>
    <div class="col-6">
        <table class="table">
            <thead>
              <tr>
                <th scope="col">#</th>
                <th scope="col">Name</th>
                <th scope="col">G-score</th>
                <th scope="col">Boost</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for='(player, index) in players' :key="index">
                <th scope="row">{{ index + 1}}</th>
                <td>{{ player.away_team.players.player_name }}</td>
                <td>{{ player.away_team.players.guessing_score.score }}</td>
                <td>{{ player.away_team.players.guessing_score.boost }}</td>
              </tr>
            </tbody>
          </table>
    </div>
</div>
  </div> -->
  </div>
</template>

<script>
// import GameList from './components/GameList.vue'
// import PlayerList from './components/PayerList.vue'

export default {

  data () {
    return {
      players: null,
      games: null
    }
  },
  created () {
    // GET data from Games list
    fetch('./data/events.json')
      .then(response => response.json())
      .then(data => (this.games = data.events))

    // GET data from Players list
    fetch('./data/players.json')
      .then(response => response.json())
      .then(data => (this.players = data.players))
  },
  components: {
    // GameList
    // PlayerList
  }
}
</script>
