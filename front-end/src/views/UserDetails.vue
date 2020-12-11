<template>
<div class="users">
  <div class="box">
    <div v-if="!edit">
        <h1>User Information:</h1>
          <ul class = "information">
      <li> Name: {{this.$root.$data.user.firstname}} {{this.$root.$data.user.lastname}}</li>
      <li>Username: {{this.$root.$data.user.username}} </li>
      <br>
      <li class = "money" > Current Balance: </li>
      <li class = "money"> <strong>${{this.$root.$data.profile.balance}}</strong></li>
      <br>
      <li> {{this.$root.$data.profile.wins}} Wins, {{this.$root.$data.profile.losses}} Losses </li>
      <br>
      <li>Total Winnings: ${{this.$root.$data.profile.balance - this.$root.$data.profile.totalDeposited}}</li>
          </ul>
      <h2 class = "button" v-on:click="addMoney=true" >CLICK HERE to add Money to your Account </h2>
      <p h2 v-if="addMoney"> Enter the amount of Money you wish to deposit below:</p>
      <input v-if="addMoney" placeholder="Please Enter Amount to Add" class = "bigger" v-model="amountToAdd">
      <button v-if="addMoney" type="submit" class="gameButton" v-on:click="addTheMoney()">Submit</button>
      <p v-if="added"> Thank You for your deposit!</p>
      <h2 class = "button" v-on:click="edit=true" >CLICK HERE to Edit your Account Information </h2>
      </div>
      <div v-if="edit">
        
      </div>
      </div>
      <div class="back"></div>
    </div>
</template>

<script>
import axios from "axios";




export default {
  name: 'UserDetails',
  data: function() {
    return {
      addMoney: false,
      amountToAdd: 0,
      error: "",
      added: false,
      edit: false
    }
  },
  components: {
  },
  methods: {
    async addTheMoney() {
      this.error = '';
      try {
        let newbalance = this.$root.$data.profile.balance + parseFloat(this.amountToAdd);
        let newDeposit = this.$root.$data.profile.totalDeposited + parseFloat(this.amountToAdd);	       
        let response = await axios.put("/api/users/" + this.$root.$data.user.username, {
                balance: newbalance,
                totalDeposited: newDeposit
          })
      this.added = true;
      this.addMoney = false;
      this.$root.$data.user = response.data.user;
      this.$root.$data.profile = response.data.profile;
      }
      catch(error) {
        console.log(error)
      }
    }	
  }
}

</script>

<style scoped>
.bigger {
  font-size: 18px;
  margin-bottom: 10px;
}

p {
  color: #b08a4f;
}

.gameButton {
    font-size: 12pt;
    border-radius: 8px;
    background-color: white;
    padding: 5px;
    margin: 20px;
    cursor: pointer;
    align-items: center;
    justify-content: center;
}

ul {
  list-style-type: none;
  font-size: 24pt;
  color: #b08a4f;
}

li {
  margin-top: 5px;
}

.back {
  min-height: 1100px;
  background-color: black;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  z-index: -2;
}

.money {
  font-size: 32pt;
}

.button {
  font-family: "Century Gothic", CenturyGothic, Geneva, AppleGothic, sans-serif;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  display: block;
  width: 70%;
  margin-top: 20px;
  margin-bottom: 50px;
  font-size: 24pt;
  border: 5px solid #b08a4f;
  cursor: pointer;
  padding: 5px;

}

.button:hover {
  background-color: #b08a4f;
  color: black;
}

.pure-button {
  background-color: black;
  color: #b08a4f;
  border-radius: 30px;
  margin-bottom: 20px;
  font-size: 18px;
  padding: 15px;
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
  font-size: 22px;
  font-variant: capitalize;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #b08a4f;
}

.black {
  background-color: black;
  width: 100%;
  height: 500px;
}

.users {
  min-height: calc(100vh - 402px);
  padding: 30px;
  padding-bottom: 0px;
  display: flex;
  justify-content: center;
}

.users::after {
content: "";
background: url(/images/user.jpg);
background-size: 100%;
background-repeat: no-repeat;
top: 0;
left: 0;
bottom: 0;
right: 0;
position: absolute;
z-index: -1;
min-height: calc(100vh - 402px);
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
  border: 5px solid #b08a4f;
}

@media (max-width:960px) {
    h1 {
        font-size: 16pt;
    }
    li {
	font-size: 12pt;
    }
    p {
	font-size: 12 pt;
    }
    .button {
	font-size: 12pt;
    }
    .money {
	font-size: 12pt;
    }
    .bigger {
	font-size: 12pt;
    } 
    .box {
	width: 80%;
    }
}
</style>
