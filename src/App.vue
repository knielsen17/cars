<template>
  <div id="app">
    <div id="nav">
      <div id="right">
        <router-link to="/">Home</router-link>
      </div>
      <div id="left">
        <router-link to="/cart">Cart</router-link>
      </div>
    </div>
    <router-view />
    <div id="footer">
      <a href="https://github.com/knielsen17/cars">Git Hub</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
    }
  },
  computed: {
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  display: flex;
  padding: 30px;
  width: 95%;
  margin: 0px 0px 30px 0px;
  border: 2px solid black;
  background-color: red;
}

#right {
  display: flex;
  justify-content: flex-start;
  flex: 1;
}

#left {
  display: flex;
  justify-content: flex-end;
  flex: 1;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
