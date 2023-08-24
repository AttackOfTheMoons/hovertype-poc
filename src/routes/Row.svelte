<script lang='ts'>
	import Key from "./Key.svelte";

    export let keys: Array<string> = [];
    export let actuationTime: number;

    let shown = false;
</script>

<style>
    div {
         display: inline-block;
    }
    .placeholder {
        float:left;
        height: 100%;
    }
    .activatorRow {
        visibility: hidden;
    }
    .row:hover .activatorRow {
        visibility: visible;
    }
</style>
<div class='row'>
    {#each keys as key}
    <div class='placeholder'>{key}</div>
    {/each}
    <div class='activatorRow'> 
        {#each keys as key}
        <Key {actuationTime} on:keyActivate value={key}/>
        {/each}
    </div>
</div>
