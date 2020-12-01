<template>
  <div id="app" class="px-10rem">
    <!--    <div id="nav">-->
    <!--      <router-link to="/">Home</router-link> |-->
    <!--      <router-link to="/about">About</router-link>-->
    <!--    </div>-->
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


.px-10rem {
  padding: 0 10rem;
}

@font-face {
  font-family: "ubuntu";
  font-style: normal;
  src: url("assets/fonts/Ubuntu-Regular.ttf");
}

@font-face {
  font-family: "ubuntu-bold";
  src: url("assets/fonts/Ubuntu-Bold.ttf");
}

@font-face {
  font-family: "dinot-regular";
  font-style: normal;
  src: url("assets/fonts/dinot.otf");
}

@font-face {
  font-family: "dinot-bold";
  font-style: normal;
  src: url("assets/fonts/DINOT-Bold.otf");
}

.ubuntu {
  font-family: ubuntu;
}

.ubuntu-B{
  font-family: ubuntu-bold;
}


.dinot {
  font-family: dinot-regular;
}

.dinot-B {
  font-family: dinot-bold;
}

.blackMDS{
  background-color:#1D1D1D !important;
  opacity: 80% !important;
}
</style>
