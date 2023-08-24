<style>
    .row {
        overflow:visible;
        width: 60vw;
        height: 5vw;
        position: relative;
    }
    .row:hover .keys {
        visibility: visible;
    }
    .keys {
        visibility: hidden;
        position: absolute;
        top:-50%;
        /* opacity: 50%; */
        /* border: 1px solid black; */
        z-index: 2;
    }
    .key {
        float: left;
        /* border: 1px solid black; */
        height: 10vw;
        
        line-height: 10vw;
        width: 10vw;
        text-align: center;
        display: flex;
        justify-content: center;
    }

    .placeholder {
        text-align: center;
        width: 10vw;
        float: left;
        height: 5vw;
        line-height: 5vw;
    }
</style>

<script lang='ts'>
    import Key from "./Key (old).svelte";
    
    export let keys: Array<string> = [];
    export let actuationTime: number;
</script>
<div class="row">
        {#each keys as value (value)}
        <div class='placeholder'>{value}</div>
        {/each}
    <div class="keys">
        {#each keys as value (value)}
        <div class='key'>
            <Key on:keyActivate {value} {actuationTime} />
        </div>
        {/each}
    </div>
</div>