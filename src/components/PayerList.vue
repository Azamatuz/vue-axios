<template>
<div class="card text-center m-3">
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
              <tr>
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
              <tr>
                <th scope="row">{{ index + 1}}</th>
                <td>{{ player.away_team.players.player_name }}</td>
                <td>{{ player.away_team.players.guessing_score.score }}</td>
                <td>{{ player.away_team.players.guessing_score.boost }}</td>
              </tr>
            </tbody>
          </table>
    </div>
</div>
  </div>
</template>

<script>
export default {
  name: 'player-list',
  props: ['player']
}
</script>
