<template>
  <div class="wrapper">
      <div class="grid">
        <div class="tile" v-for="tile in tiles" :key="tile.id" v-bind:style="{'background-image': 'url' + '(' + require('./images/' + tile.path) +')' }" @mouseover="this.activeTile = tile"></div>
      </div>
      <div class="tile-detail">
        <h1>{{ activeTile.title }}</h1>
        <h3>{{ activeTile.materials }}</h3>
        <p>{{ activeTile.owner }}</p>
        <p class="description">{{ activeTile.description }}</p>
        <p class="email"><i>{{ activeTile.email }}</i></p>
      </div>
  </div>

</template>

<script>
import tiles from './tiles.json'
export default {
  name: 'App',
  data() {
    return {
      tiles: tiles,
      activeTile: {}
    }
  }
}
</script>

<style>
.activeTile {
  border-radius: 5px;
  z-index: 1000;
  transform: scale(1.2);
  box-shadow: rgba(0, 0, 0, 0.527) 0px 10px 50px;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
}
.wrapper {
    display: flex;
}

.grid { 
    width: 100vh !important;
    height: 100vh;
    display: grid; 
    grid-template-columns: repeat(4, 1fr); 
    grid-template-rows: repeat(4, 1fr); 
    grid-column-gap: 10px;
    grid-row-gap: 10px; 
    margin-right: 2vw;
}

.tile {
    transition: 350ms cubic-bezier(0.16, 0, 0.29, 1.58);
    cursor: pointer;
    height: 100%;
  background-size: cover; /* <-- background size */
  background-position: center; /* <-- background position */
}

.tile:hover {
  border-radius: 5px;
  z-index: 1000;
    transform: scale(1.2);
    box-shadow: rgba(0, 0, 0, 0.527) 0px 10px 50px;
}

.tile-detail {
  max-width: 30vw;
}

@font-face {
    font-family: 'PP Eiko';
    src: url('./fonts/otf/PPEiko-LightItalic.otf') format('opentype'),
        url('./fonts/woff/PPEiko-LightItalic.woff') format('woff');
    font-weight: 200;
    font-style: italic;
}

@font-face {
    font-family: 'PP Eiko';
    src: url('./fonts/otf/PPEiko-Thin.otf') format('opentype'),
        url('./fonts/woff/PPEiko-Thin.woff') format('woff');
    font-weight: 100;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Black.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Black.WOFF') format('woff');
    font-weight: 900;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-BlkIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-BlkIt.WOFF') format('woff');
    font-weight: 900;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Bold.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Bold.WOFF') format('woff');
    font-weight: 700;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-BdIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-BdIt.WOFF') format('woff');
    font-weight: 700;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Medium.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Medium.WOFF') format('woff');
    font-weight: 500;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-MedIta.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-MedIta.WOFF') format('woff');
    font-weight: 500;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Reg.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Reg.WOFF') format('woff');
    font-weight: 400;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Italic.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Italic.WOFF') format('woff');
    font-weight: 400;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-SemLt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-SemLt.WOFF') format('woff');
    font-weight: 350;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-SmLtIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-SmLtIt.WOFF') format('woff');
    font-weight: 350;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Light.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Light.WOFF') format('woff');
    font-weight: 300;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-LtIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-LtIt.WOFF') format('woff');
    font-weight: 300;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-ExLtIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-ExLtIt.WOFF') format('woff');
    font-weight: 200;
    font-style: italic;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-Thin.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-Thin.WOFF') format('woff');
    font-weight: 100;
    font-style: normal;
}

@font-face {
    font-family: 'Neue Haas Grotesk Display';
    src: url('./fonts/otf/NeueHaasGroteskDisplay-ThIt.otf') format('opentype'),
        url('./fonts/woff/NeueHaasGroteskDisplay-ThIt.WOFF') format('woff');
    font-weight: 100;
    font-style: italic;
}

::selection {
    color: #fff;
    background-color: #000;
}

::-moz-selection {
    /* Code for Firefox */
    color: #fff;
    background-color: #000;
}


i {
    font-style: italic;
}

body {
    font-family: 'Neue Haas Grotesk Display', 'Helvetica Neue', -apple-system, BlinkMacSystemFont, 'Neue Montreal', Helvetica, Arial, sans-serif;
    color: #000;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    /* background-color: #F5F5F2; */
    background-color: #fff;
    /* background-color: rgb(255, 252, 245)    ; */
    /* font-size: 21px; */
    /* font-size: 20px; */
    /* font-size: 1.25vw; */
    font-size: 18px;
    font-weight: 400;
    line-height: 1.1818;
}

p {
    overflow-wrap: break-word;
    font-size: 1.8vw;
    line-height: 2vw;
    font-weight: 400;
    margin-top: 10px;
}

h1 {
    font-size: 4.3vw;
    letter-spacing: -0.2vw;
    font-weight: 500;
    text-transform: uppercase;
    line-height: 4vw;
    margin: 30px 0px 20px 0px;
}

h2 {
    font-size: 4.8vw;
    line-height: 5vw;
    letter-spacing: -0.1vw;
}
h3 {
  margin-bottom: 60px;
  text-transform: uppercase;
  font-weight: 400;
  font-size: 1.4vw;
  letter-spacing: 1px;
}
.email {
  margin-top: 60px;
}
</style>
