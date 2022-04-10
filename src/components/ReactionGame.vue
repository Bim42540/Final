<script>


export default {
    
    data() {
        return {
            counter: 0,
        }
    },
    
    methods: {
        moveCircleOnClick() {
           let circle = document.querySelector('.ReactionGameCircle');
           let mainDiv = document.querySelector('.ReactionGameMainDiv');
           circle.style.left = Math.random() * ((mainDiv.offsetWidth - 50) - circle.offsetWidth) + 'px';
           circle.style.top = Math.random() * ((mainDiv.offsetHeight - 100) - circle.offsetHeight) + 'px';
        },

        scoreCounter() {
            this.counter++;
            console.log(mainDiv.offsetWidth, mainDiv.offsetHeight);
        },

    },
}
</script>

<template>
    <div class="ReactionGameMainDiv">
        <div class="ReactionGameCircle" @click="moveCircleOnClick(), scoreCounter()">
        </div>
    </div>
        <p>Score: {{counter}}</p>
</template>


<style>
    .ReactionGameMainDiv {
     height: 70vh;
     width: 100%;
     border: 1px solid red; 
     z-index: 1;  
    }

    .ReactionGameCircle{
        height: 50px;
        width: 50px;
        border-radius: 50%;
        background-color: red;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 50;
    }
</style>