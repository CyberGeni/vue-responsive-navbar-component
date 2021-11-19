<template>
  <div id="app">
    <header>
    <h1>sunnyside</h1>
    <nav>
      <button @click="toggle = !toggle" v-if="!toggle" :class="{toggle: !toggle}"><img src="images/icon-hamburger.svg" alt=""></button>
      <button @click="toggle = !toggle" v-if="toggle">X</button>
      <ul v-if="toggle" :class="{toggle: !toggle}">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      toggle: false
    }
  },
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    font-family: 'Arial Narrow Bold', sans-serif;
  }
  body {
    background: dodgerblue;
    overflow: hidden;
  }
  header {
    display: flex;
    justify-content: space-between;
  }
  h1 {
    margin: 24px;
    color: white;
  }
  button {
    height: fit-content;
    padding: 10px 15px;
    margin: 24px;
    background: #00000000;
    border: none;
    color: dodgerblue;
  }
  button:last-of-type {
    position: absolute;
    font-size: 30px;
    right: 0;
  }
  ul {
    display: grid;
    color: gray;
    z-index: 10;
    width: 50vh;
    height: 100vh;
    background: #fff;
    place-content: center;
    text-align: center;
    line-height: 35px;
    animation: menu 500ms;
  }
  li, a {
    color: gray;
    text-decoration: none;
    list-style: none;
  }
  @keyframes menu {
    0% {
      width: 0px;
    }
    100% {
      width: 50vh;
    }
  }
  @media  screen and (min-width: 600px) {
    button {
      display: grid;
    }
    ul {
      display: flex;
      margin: 24px;
      color: gray;
      z-index: 10;
      width: 50vh;
      height: auto;
      background: #fff;
      place-content: center;
      text-align: center;
      line-height: 35px;
      animation: menu 500ms;
    }
  }
</style>

