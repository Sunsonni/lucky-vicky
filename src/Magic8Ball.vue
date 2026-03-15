<script setup>
    import { ref } from 'vue';

    const responses = [
        "Yes, definitely.",
        "As I see it, yes.",
        "Reply hazy, try again.",
        "Cannot predict now.",
        "Do not count on it.",
        "My sources say no.",
        "Outlook not so good.",
        "Very doubtful."
    ]

    const response = ref('');

    const getResponse = () => {
        const randomArrayIndex = Math.floor(Math.random() * responses.length)
        
        response.value = responses[randomArrayIndex];
    }
</script>

<template>
    <h1 class="flex justify-center">Ask Magic 8 Ball a Question</h1>
    <div 
    class="ball"
    @click="getResponse"
    >
        <div class="window">
            <p class="text">{{ response }}</p>
        </div>
    </div>
</template>

<style>

.ball{
    width:250px;
    height:250px;
    background:black;
    border-radius:50%;
    display:flex;
    justify-content:center;
    align-items:center;
    cursor:pointer;
    margin:auto;
    box-shadow: 0 10px 30px rgba(0,0,0,.4);
}

.ball:hover{
    transform:scale(1.05);
    transition:.2s;
}

.window{
    width:120px;
    height:120px;
    background:#1e3a8a;
    border-radius:50%;
    display:flex;
    justify-content:center;
    align-items:center;
}

.text{
    color:white;
    text-align:center;
    font-weight:bold;
    padding:10px;
}

.ball:active{
    animation: shake .3s;  
}

@keyframes shake{
    0%{ transform:rotate(0deg); }
    25%{ transform:rotate(3deg); }
    50%{ transform:rotate(-3deg); }
    75%{ transform:rotate(2deg); }
    100%{ transform:rotate(0deg); }
}

</style>