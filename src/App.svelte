<script>
    import { fade, blur, slide, scale } from "svelte/transition";
    let numbers = [];

    function addNumber(){
        numbers.push(Math.floor(Math.random()*100));
        numbers = numbers;
    }
</script>

<div class="container">
    <h1>Number:</h1>
    <div>
        {#each numbers as number,i(number)}
            <button class="element" transition:scale>
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