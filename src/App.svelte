<script>
    import { tweened, spring } from "svelte/motion";
    import { bounceIn } from "svelte/easing";

    let value = spring(1,{
        stiffness:1, // 0/1 thightness
        damping:0.2, // 0/1 springy
        precision: 0.1 // when it stops
    });
    function tweenValue(){
        $value = 2;
    }
</script>

<div class="container">
   <div
    class="square"
    style="transform: scale({$value});"
   ></div>
   <button on:click={tweenValue}>Tween value</button>
</div>

<style>
  .square{
    display: block;
    background: red;
    width: 100px;
    height:100px
  }
</style>