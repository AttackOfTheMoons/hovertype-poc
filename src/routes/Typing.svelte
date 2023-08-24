<style>
    input {
        min-width: 38em;
        height: 2em;
        margin-bottom: 1em;
        background: #985F99;
        color: #ffffff;
    }
</style>

<script lang='ts'>
    import Keyboard from "./Keyboard.svelte";

    let inputVal = '';
    let actuationTime = 300;
</script>

<input type="text" bind:value={inputVal}>
<Keyboard on:keyActivate={(event) => {inputVal += event.detail.value}} {actuationTime}/>