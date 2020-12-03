<template>
  <div id="app">
    <!--    <div id="nav">-->
    <!--      <router-link to="/">Home</router-link> |-->
    <!--      <router-link to="/about">About</router-link>-->
    <!--    </div>-->
    <router-view/>
  </div>
</template>

<style>

*:focus{
  border: solid red 4px !important;
}
#app {
  font-family: gotham,Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

button:focus {
  border: none  ;
}

.px-10rem {
  padding: 0 10rem;
}

.w-80{
  width: 80%;
}

.px-5rem{
  padding: 0 5rem;
}

@font-face {
  font-family: "ubuntu";
  font-style: normal;
  src: url("assets/fonts/Ubuntu-Regular.ttf");
}

@font-face {
  font-family: "ubuntu-bold";
  src: url("assets/fonts/UbuntuMono-Bold.ttf");
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

@font-face {
  font-family: 'gotham';
  src: url("assets/fonts/GothamRounded-Book.otf");
}

.ubuntu {
  font-family: ubuntu;
}

.ubuntu-B{
  font-family: ubuntu-bold !important;
}

h2.ubuntu-B{
  font-size: 2rem !important;
}

h3.ubuntu-B{
  font-size: 1.8rem;
}
p.ubuntu-B{
  font-size: 1.3rem !important;
}

.dinot {
  font-family: dinot-regular;
}

.dinot-B {
  font-family: dinot-bold;
}

.gotham{
  font-family: gotham;
}

.blackMDS{
  background-color:#1D1D1D !important;
  opacity: 95% !important;
}


.buttonMDS{
  border-radius: 0 !important;
  margin: 0 2rem;
}

.bg-grey{
  background-color: #F5F5F5;
}

.breadcrumb {
  background-color: white !important;
}

.breadcrumb ul {
  display: flex;
  list-style-type: none;
}

.breadcrumb li::before {
  content: ">";
  margin-left: 1rem;
  margin-right: 1rem;
}

.breadcrumb li:first-child::before {
  content: "";
}

.text-black{
  color:black !important;
}
</style>
