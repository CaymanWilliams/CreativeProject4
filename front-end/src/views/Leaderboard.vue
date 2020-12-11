<template>
  <div class="leaderboard">
    <div class="box">
      <h1>Leaderboard</h1>
      <div class = "players">
        <li v-for="leader in leaders" :key="leader.username">
          Username: {{leader.username }} Wins: {{leader.wins}}
        </li>
        </div>
      <h2>These are the top Champion Casino BlackJack Players in the World</h2>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Home',
  components: {
  },
  data:
    function() {
      return {
        leaders: []
      }
    },
  asyncComputed: {
    async leaders() {
      function sortfunction(a,b) {
        return b.wins - a.wins
      }
      try {
        let response = await axios.get('/api/users', {})
        var userranking = response.data
        userranking = userranking.sort(sortfunction)
        if (userranking.length > 5) {
          console.log(userranking.slice(5))
          return userranking.slice(5)
        }
        else {
          console.log(userranking)
          return userranking
        }
      }
      catch(error) {
        return error
      }
    }
  },
  methods: {
  }
}
</script>

<style scoped>

.players {
  color: white;
}

h1 {
  font-size: 48px;
  font-variant: capitalize;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #b08a4f;
  margin-bottom: 20px;
  background-color: black;
  padding: 10px;
}

h2 {
  font-size: 38px;
  font-variant: capitalize;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #b08a4f;
  margin-bottom: 20px;
  margin-top: 80px;
}


.leaderboard {
  padding: 30px;
  display: flex;
  justify-content: center;
}

.leaderboard::after {
content: "";
background: url(/images/leaderboard.jpg);
background-size: 100%;
background-repeat: no-repeat;
top: 0;
left: 0;
bottom: 0;
right: 0;
position: absolute;
z-index: -1;
}

.box {
  background: black;
  opacity: 0.95;
  width: 50%;
  padding: 20px;
  font-size: 20px;
  text-align: center;
  border-radius: 5px;
  justify-content: center;
  text-align: center;
  display: inline;
}

</style>
