<template>
<div class="users">
  <div class="box">
    <h1>User Information:</h1>
    <div v-if="error" class = "error"> <h1> Please Login or Register to view user data </h1></div>
    <div v-else>
      <h2>(use the buttons to modify the information as necessary)</h2>
      <div class = "information">{{information}}THERE WILL BE A LIST HERE</div>
    </div>

  </div>
</div>
</template>

<script>
export default {
  name: 'Table',
  components: {
  },
}

</script>

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
  font-size: 22px;
  font-variant: capitalize;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #b08a4f;
}


.users {
  padding: 30px;
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
