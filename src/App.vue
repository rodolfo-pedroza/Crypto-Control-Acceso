<template>
  <div class="navbar navbar-dark bg-primary">
    <a href="" class="navbar-brand p-2">Registro Crypto</a>
    <ul class="nav">
      <li class="nav-item p-2">
        <router-link to="/" class="text-white">Home</router-link> 
      </li>
      <li class="nav-item p-2">
        <router-link to="/login" class="text-white">Login</router-link>
      </li>
      <li class="nav-item p-2">
        <router-link to="/signup" class="text-white">Sign Up</router-link>
      </li>
    </ul>
  </div>
  <div class="container py-4">
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
