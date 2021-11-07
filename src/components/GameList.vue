<template>
<div class="card text-center m-3">
    <h5 class="card-header">Games List</h5>
            <table class="table">
            <tr v-for='(game, index) in games' :key="index">
                <td>{{ index + 1}}</td>
                <td>
                    <table class="table">
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
</template>

<script>
export default {
  name: 'game-list',
  props: ['games']
}
</script>
