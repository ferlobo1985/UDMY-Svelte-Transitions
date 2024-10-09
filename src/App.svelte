<script>
    import { fade, blur, slide, scale, fly } from "svelte/transition";
    import { bounceIn, elasticIn } from "svelte/easing";
    import { flip } from "svelte/animate";
    let numbers = [];

    function addNumber(){
        numbers.push(Math.floor(Math.random()*100));
        numbers = numbers;
    }
    function removeNumber(i){
        numbers.splice(i,1);
        numbers = numbers;
    }
</script>

<div class="container">
    <h1>Number:</h1>
    <div>
        {#each numbers as number,i(number)}
            <button 
                class="element"
                on:click={()=>removeNumber(i)} 
                transition:fade={{ duration:500 }}
                animate:flip={{
                    delay:0,
                    duration:300,
                    easing:bounceIn
                }}
            >
                {number}
            </button>
        {/each}
    </div>
    <hr/>
    <button on:click={addNumber}>Add a button</button>
</div>

<style>
    .element {
        width: 100%;
        padding: 10px;
        margin:5px
    }
</style>