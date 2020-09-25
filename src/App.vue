<template>
  <div id="app">
    <!-- <div id="nav">
       <router-link to="/">Login</router-link>|
      <router-link to="/about">About</router-link> 
    </div> -->
    <router-view />
  </div>
</template>

<style>
#app {
  @import url("https://fonts.googleapis.com/css?family=Roboto+Condensed");
  font-family: "Open Sans";
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  /* color: #2c3e50; */
}

#nav {
  padding: 20px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #00acc2;
}
</style>
