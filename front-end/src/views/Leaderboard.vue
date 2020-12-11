<template>
  <div>
  <div class="leaderboard">
    <div class="box">
      <h1>Leaderboard</h1>
      <div class = "players">
        <ul>
          <li v-for="(leader, index) in leaders" :key="leader.username" class = "listitem">
            <h1 style="display:inline">{{index+1}}) {{leader.username }}: {{leader.wins}} Wins</h1>
          </li>
        </ul>
      </div>
      <h2>These are the top Champion Casino BlackJack Players in the World</h2>
    </div>
  </div>
    <div class="back">
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
          return userranking.slice(0,5)
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
.players ul{
  list-style-type: none;
  padding-left: 0;
}

li {
  white-space: pre;
}

.box {
  border: 5px solid #b08a4f;
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
  margin-top: 20px;
}

.back {
  min-height: calc(100vh - 555px);
  background-color: black;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  z-index: -2;
}

.leaderboard {
  padding: 30px;
  display: flex;
  justify-content: center;
}

.listitem {
  padding:10px;
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

@media only screen and (max-width: 960px) {
  h1 {
    font-size: 12pt;
  }
  ul {
    font-size: 10pt;
  }
  h2 {
    font-size: 12pt;
  }
}

</style>
