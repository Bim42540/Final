<script>
export default {
  methods: {
    redirectToTimerBlock() {
      this.$router.push('/timerBlock');
    },
    redirectToReactionGame() {
      this.$router.push('/reactionGame');
    }    
  },
}
</script>

<template>
  <div class="WelcomeDivMain">
    <h1 class="WelcomeText">Code Academy Project</h1>
    <button class="WelcomeButtons" @click="redirectToTimerBlock()">Reaction time check</button>
    <button class="WelcomeButtons" @click="redirectToReactionGame()">Reaction time trainer</button>
  </div>
</template>

<style>
  .WelcomeDivMain {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .WelcomeText {
    margin-top: 50px;
    margin-bottom: 50px;
  }

  .WelcomeButtons {
    height: 50px;
    width: 150px;
    border-radius: 5px;
    background-color: #33658A;
    border: none;
    margin-bottom: 50px;
    transition-duration: 0.4s;
  }

  .WelcomeButtons:hover {
    background-color: #86BBD8;
    color: white;
  }

 

</style>