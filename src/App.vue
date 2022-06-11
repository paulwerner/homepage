<template>
  <v-app id="app">
    <NavBar id="nav" />
    <v-content class="font">
      <router-view />
    </v-content>
    <Footer id="footer" />
  </v-app>
</template>

<script>
import NavBar from "./components/NavBar";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: { NavBar, Footer },
  data: () => ({
    //
  }),
};
</script>

<style>
html,
body {
  height: 100%;
  padding: 0;
  margin: 0;
  overflow: hidden;
}

a:link {
  color: #f4e4c0;
}

a:visited {
  color: #f3ca84;
}

a:hover {
  color: #ae8d67;
}

a:active {
  color: #be884b;
}

h1 {
  font-weight: bold;
  font-size: 32px;
}

h2 {
  font-weight: bold;
  font-size: 24px;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100%;
  height: 100%;
  overflow: auto;

  background-position: top;
  background-repeat: no-repeat;
  background-size: contain;
  position: absolute;
  background-color: #0f0b07;

  background-image: -webkit-linear-gradient(
      top,
      rgba(125, 185, 232, 0) 0%,
      rgb(15, 11, 7) 100%
    ),
    url(./assets/background.png);
  background-image: -moz-linear-gradient(
      top,
      rgba(125, 185, 232, 0) 0%,
      rgb(15, 11, 7) 100%
    ),
    url(./assets/background.png);
  background-image: -o-linear-gradient(
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 1) 100%
    ),
    url(./assets/background.png);
  background-image: -ms-linear-gradient(
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 1) 100%
    ),
    url(./assets/background.png);
  background-image: linear-gradient(
      to bottom,
      rgba(125, 185, 232, 0) 0%,
      rgb(15, 11, 7) 100%
    ),
    url(./assets/background.png);
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#1e5799', endColorstr='#007db9e8', GradientType=0); /* IE6-9 */
}

.content-container {
  background-color: #0f0b07;
  border-radius: 5px;
  border-width: 4px;
  border-color: #be884b;
  border-style: solid;
  -webkit-box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
  -moz-box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
  box-shadow: 9px 8px 11px -4px rgba(0, 0, 0, 0.3);
  margin: 24px auto 24px auto;
  width: 80%;
  max-width: 800px;
  padding: 20px;
}

@font-face {
  font-family: TravelingTypewriter;
  src: url(./assets/font/TravelingTypewriter.otf);
}

.font {
  color: #d8d6cf;
  font-weight: normal;
  font-size: 18px;
  font-family: TravelingTypewriter, sans-serif;
}
</style>
