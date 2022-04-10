<script>
import TimerBlock from '../components/TimerBlock.vue'

export default {
	name: 'TimerBlockView',
  	components: { TimerBlock },
	data() {
		return {
		isPlaying: false,
		delay: null,
		timerBlockScore: null,
		showTimerBlockResults: false
		}
	},


	methods: {
		start() {
			this.delay = 2000 + Math.random() * 5000;
			this.isPlaying = true;
			this.showTimerBlockResults = false;
		},
		endTimerBlock(reactionTime) {
			this.timerBlockScore = reactionTime;
			this.isPlaying = false;
			this.showTimerBlockResults = true;
		}
	}
}

</script>


<template>

    <div class="reactionTimeBlockMainDiv">
        <h1 class="ReactionTimerH1Text">Reaction Timer</h1>
        <p>Click on the play button</p>
        <p class="ReactionTimerBlockExplanationText">Click on the square below the play button as soon as it appears</p>
        <button class="ReactionTimerButton" @click="start" :disabled="isPlaying">Play</button>
        <TimerBlock class="ReactionTimerBlock" v-if="isPlaying" :delay="delay" @end="endTimerBlock"/> 
        <p class="ReactionTimerScore" v-if="showTimerBlockResults">reaction time: {{ timerBlockScore }} ms</p> 
    </div>

    <RouterView />
</template>

<style>
@import '@/assets/base.css';

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

  .ReactionTimerH1Text {
	text-align: center;
	margin-bottom: 50px;
	margin-top: 50px;
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

.reactionTimeBlockMainDiv {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.ReactionTimerBlockExplanationText{
	margin-bottom: 20px;
}
  
}


</style>
