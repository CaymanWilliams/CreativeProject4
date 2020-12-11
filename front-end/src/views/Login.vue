<template>
<div class="hero">
  <div class="heroBox">
    <h1>Join the Game</h1>
    <form class="pure-form">
      <div>
        <h2>Register for an account</h2>
        <input placeholder="First Name" class = "bigger" v-model="firstName">
        <input placeholder="Last Name" class = "bigger" v-model="lastName">
      </div>
      <div>
        <input placeholder="username"  class = "bigger" v-model="username">
        <input type="password" placeholder="password" class = "bigger" v-model="password">
      </div>
      <div>
        <button type="submit" class="pure-button" @click.prevent="register">Register</button>
      </div>
    </form>
    <p v-if="error" class="error">{{error}}</p>
    <form class="pure-form">
    <div>
      <h2>Login</h2>
      <input placeholder="username" class = "bigger" v-model="usernameLogin">
      <input type="password" placeholder="password" class = "bigger" v-model="passwordLogin">
    </div>
    <div>
      <button type="submit" class="pure-button" @click.prevent="login">Login</button>
    </div>
  </form>
  <p v-if="errorLogin" class="error">{{errorLogin}}</p>
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
}

.bigger {
  font-size: 32px;
  margin-bottom: 20px;
}


.hero {
  padding: 30px;
  display: flex;
  justify-content: center;
}

.pure-button {
  background-color: black;
  color: #b08a4f;
  border-radius: 30px;
  margin-bottom: 20px;
  font-size: 30px;
  padding: 15px;
}

.heroBox {
  background: white;
  opacity: 0.95;
  display: inline;
  padding: 20px;
  font-size: 20px;
  text-align: center;
  border-radius: 30px;
}

.hero::after {
content: "";
background: url(/images/car.jpg);
background-size: 100%;
background-repeat: no-repeat;
top: 0;
left: 0;
bottom: 0;
right: 0;
position: absolute;
z-index: -1;
}

.hero img {
height: 20px;
margin: 0px;
}


.hero form {
  font-size: 14px;
}

.hero form legend {
  font-size: 20px;
}

input {
  margin-right: 10px;
}

.error {
  margin-top: 20px;
  display: inline;
  padding: 5px 20px;
  border-radius: 30px;
  font-size: 10px;
  background-color: #d9534f;
  color: #fff;
}
</style>
