<script >
import { RouterLink, RouterView } from 'vue-router'


</script>


<template>

<nav>
  <img src="./assets/codeacademy-white.svg" alt="code-academy-img">
  <RouterLink to="/">Home</RouterLink>
  <RouterLink to="/about">About</RouterLink>
  <RouterLink to="/timerBlock">Timer Block</RouterLink>
  <RouterLink to="/reactionGame">Reaction Game</RouterLink>
</nav>

 
  <RouterView />

  <footer>
    <p class="FooterText"> © 2022 CodeAcademy Project</p>
  </footer>
</template>

<style>
@import '@/assets/base.css';


header {
  line-height: 1.5;
  max-height: 100vh;
}


a,
.green {
  text-decoration: none;
  color: 444;
  transition: 0.4s;
}

.ReactionTimerH1Text {
  text-align: center;
  margin-bottom: 100px;
}

.ReactionTimerButton {
  /* display: block; */
  margin: 0 auto 50px auto;
  height: 50px;
  width: 200px;
  border-radius: 10%;
  border-color: yellow;
  background-color: yellow;
}

.ReactionTimerBlock {
  margin: 0 auto;
}

.ReactionTimerScore {
  font-size: 25px;
}

footer {
   position:absolute;
   bottom:0;
   text-align: center;
   width:100%;
   height:40px;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {

  #app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

  body {
    display: flex;
    justify-content: center;
    /* flex-flow: row; */
  }

  /* #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  } */

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}


</style>
