<style>

    .big {
        text-align: center;
        /* border: 1px solid black; */
        color: white;
        overflow: hidden;
        display: flex;
        justify-content: center;
    }
    .background {
        top: 0;
        left: 0;
        z-index: -2;
        height: 100%;
        width: 100%;
        position: absolute;
        background-color: blue;
    }
    .big:hover .color {
    opacity: 1;
    width: 150%;
    height: 150%;
    top: -25%;
    left: -25%;
  }

    .color {
        background: red;
        border-radius: 50%;
        height: 0;
        width: 0;
        position: absolute; /* Position it absolutely within the big div */
        top: 50%;
        left: 50%;
        z-index: -1;
        opacity: 0;
        transition: width 0.2s ease, height 0.2s ease, top 0.2s ease, left 0.2s ease, opacity 0s;
        margin: auto;
    }
   
</style>

<script lang='ts'>
    import { createEventDispatcher, onDestroy } from "svelte";
    export let value = '';
    export let actuationTime: number;
    const dispatch = createEventDispatcher();
    let timer: NodeJS.Timeout;
    let stopped = false;
    const handleMouseMove = () => {
        if (stopped) 
        return;
        clearTimeout(timer);
        stopped = false;
        timer = setTimeout(() => {
            if (stopped == true) {
                return;
            }
            dispatch('keyActivate', {value});
            stopped = true;
        }, actuationTime);
     };
    const handleMouseLeave = () => {
        stopped = false;
        clearTimeout(timer);
    }
    onDestroy(() => {
        clearTimeout(timer);
    });
</script>

<div id={value} class="big"
    role="region"
    aria-label={`Activates the key ${value}`}
    on:mousemove={handleMouseMove}
    on:mouseleave={handleMouseLeave}
>
    <span>{value}</span>
    <div class="color"></div>
    <div class='background'></div>
</div>