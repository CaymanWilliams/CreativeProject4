<template>
  <div class="home">

  <img class = "title" src=/images/logo.jpg>

  <img class = "title2" src=/images/cards.jpg>

  <div class = "welcome">
    <h1><strong>Welcome to Champion Casino</strong></h1>
    <p>Champion Casino is renowned for being the world's leader in online BlackJack.
    Begin a game by clicking the button below:</p>
  </div>

  <p class = "button"><router-link to="/Table"> Click to Enter the BlackJack Table </router-link></p>

  <img class = "title2" src="/images/table.jpg">

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
// @ is an alias to /src
export default {
  name: 'Home',
  components: {
  }
}
</script>

<style scoped>
.home {
  background-color: #000000;
}

.title {
  display: block;
  margin-right: auto;
  margin-left: auto;
}

.title2 {
  display: block;
  margin-right: auto;
  margin-left: auto;
  margin-top: 30px;
  margin-bottom: 30px;
  width: 85%;
}

.welcome {
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
  text-align: center;
  color: black;
  background: linear-gradient(rgb(78, 138, 105), white );
  border: 5px solid #b08a4f;
  margin: 50px;
  padding:10px;
}

.button {
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  display: block;
  width: 30%;
  margin-top: 20px;
  margin-bottom: 50px;
  font-size: 24pt;
  border: 5px solid #b08a4f;
}

footer {
  background-color: #000000;
  border-top: 5px solid #b08a4f;
  border-bottom: 5px solid #b08a4f;
  text-align: center;
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
  margin-top: 50px;
  color: #b08a4f;
}

h5 {
  font-size: 24pt;
  margin: 0px;
}

#menu {
  list-style-type: none;
}

p a {
  display: block;
  color: #b08a4f;
  text-align: center;
  padding: 8px 10px;
  text-decoration: none;
  font-weight: bold;
}

p a:hover {
  color: #000000;
  background-color: #b08a4f;
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

@media only screen and (max-width: 990px) {
  li a {
    font-size: 8pt;
  }
  footer {
    font-size: 8pt;
  }
  .button {
    font-size: 12pt;
  }

}

@media only screen and (min-width: 991px) {
  .welcome {
    font-size: 24pt;
  }
  h1 {
    font-size: 40pt;
  }

}

</style>
