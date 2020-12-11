<template>
  <div id="app">
    <div id="nav">
      <a v-if="this.$root.login" style="color:black;"> Login </a>
      <a v-if="!this.$root.login" style="color:black;">Sign Out</a>
      <router-link to="/">Home</router-link> |
      <router-link to="/Table">Table</router-link> |
      <router-link to="/Leaderboard">Leaderboard</router-link> |
      <router-link to="/UserDetails">User Details</router-link>
      <router-link to="/Login" v-if="this.$root.login" style="float:right;">Login</router-link>
      <a href="/" style="float:right;" v-if="!this.$root.login" v-on:click = "SignOut()"> Sign Out</a>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  methods: {
    SignOut() {
      console.log("sign out attempted")
      this.user = null;
    }
  }
}
</script>

<style>
* {
  margin: 0;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav{
  padding: 30px;
  background: black;
  font-size: 24pt;
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
}

#nav a {
  font-weight: bold;
  color: #b08a4f;
  padding-left: 5px;
  padding-right: 5px;
}

#nav a.router-link-exact-active{
  color: #497834;
}

@media only screen and (max-width: 990px) {
#nav{
  font-size: 16pt;
}

}
</style>
