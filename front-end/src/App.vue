<template>
  <div id="app">
    <div id="nav">
      <a v-if="this.$root.login" style="color:black;"> Login </a>
      <a v-if="!this.$root.login" style="color:black;">Sign Out</a>
      <router-link to="/" class="Home">Home</router-link><span v-if="!this.$root.login">|</span>
      <router-link to="/Table" v-if="!this.$root.login">Table</router-link><span v-if="!this.$root.login">|</span>
      <router-link to="/Leaderboard" v-if="!this.$root.login" >Leaderboard</router-link><span v-if="!this.$root.login">|</span>
      <router-link to="/UserDetails" v-if="!this.$root.login" >User Details</router-link>
      <router-link to="/Login" v-if="this.$root.login" style="float:right;">Login</router-link>
      <a href="/" style="float:right;" v-if="!this.$root.login" v-on:click = "SignOut()"> Sign Out</a>
    </div>
    <router-view/>
    <footer>
    <div class="part-one">
        <ul id="menu">
          <li><a href="https://github.com/CaymanWilliams/CreativeProject4">GitHub Repository (URL: https://github.com/CaymanWilliams/CreativeProject4) </a></li>
        </ul>
    </div>
    <div class="part-two">
      Created by Cayman Williams and Joseph Wesley Fairbanks <br><br>
      All rights reserved © 2020 Champion Casino
    </div>
  </footer>
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

footer {
  background-color: #000000;
  border-top: 5px solid #b08a4f;
  border-bottom: 5px solid #b08a4f;
  text-align: center;
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
  color: #b08a4f;
}

li a {
  display: block;
  color: #b08a4f;
  text-align: center;
  padding: 8px 10px;
  text-decoration: none;
  font-size: 12pt;
  margin-right: 30px;
}

li a:hover {
  color: #000000;
  background-color: #b08a4f;
}

.part-two {
  padding-bottom: 25px;
}

#menu {
  list-style-type: none;
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
