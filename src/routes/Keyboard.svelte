<style>
    * {
        font-size: 2em;
    }
</style>

<script lang='ts'>
    import Row from "./Row.svelte";
    export let actuationTime: number;
</script>

<div>
    <Row {actuationTime} on:keyActivate keys={['a', 'b', 'c', 'd', '1', '2']} />
    <Row {actuationTime} on:keyActivate keys={['e', 'f', 'g', 'h', '3', '4']} />
    <Row {actuationTime} on:keyActivate keys={['i', 'j', 'k', 'l', 'm', 'n']} />
    <Row {actuationTime} on:keyActivate keys={['o', 'p', 'q', 'r', 's', 't']} />
    <Row {actuationTime} on:keyActivate keys={['u', 'v', 'w', 'x', 'y', 'z']} />
    <Row {actuationTime} on:keyActivate keys={['5', '6', '7', '8', '9', '0']} />
</div>