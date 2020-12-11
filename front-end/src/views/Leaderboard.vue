<template>
  <div class="leaderboard">
    <div class="box">
      <h1>Leaderboard</h1>
      <div class = "players">{{leaders}}THERE WILL BE A LIST HERE</div>
      <h2>These are the top ten Champion Casino Black Jack Players in the World</h2>
    </div>
  </div>
</template>

<style scoped>

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
