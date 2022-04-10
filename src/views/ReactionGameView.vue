<script>

import ReactionGame from '../components/ReactionGame.vue'

export default {
    name: 'ReactionGameView',
    components: { ReactionGame },
    data() {
        return {
            isPlaying: false,
        }
    },

    methods: {
        start() {
            this.isPlaying = true;
        }
    },
    
}
</script>

<template>
    <div id="mainDiv" class="reactionGameMainDivBeforeStart">
        <div v-if="!isPlaying">
            <p class="ReactionGameText ReactionGameTextMT">Press Start button to start</p>
            <p class="ReactionGameText">Click on red circle to earn points</p>
            <button class="reactionGamePlayButton" @click="start">Start</button>
        </div>
      
        <ReactionGame v-if="isPlaying"/> 
    </div> 
   <RouterView />
</template>



<style>
@import '@/assets/base.css';

.reactionGameMainDivAfterStart {
    height: 70vh;
    width: 100%;
    border: 1px solid red; 
    z-index: 1;  
}

.ReactionGameText {
    text-align: center;
    margin-bottom: 20px;
}

.reactionGameMainDivBeforeStart {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.reactionGamePlayButton {
    /* display: block; */
    margin: 100px auto 50px auto;
    height: 50px;
    width: 200px;
    border-radius: 10%;
    border-color: yellow;
    background-color: yellow;
}

.ReactionGameTextMT {
    margin-top: 80px;
}

#app {
  width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

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
  body {
    display: flex;
    justify-content: center;
    /* align-items: center; */
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