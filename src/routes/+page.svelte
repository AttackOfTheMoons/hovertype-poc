<script>
    import Keyboard from "./Keyboard.svelte";
	import Typing from "./Typing.svelte";
    import Test from "./Key.svelte";
	import TestTwo from "./Row.svelte";
	import Row from "./Row (old).svelte";

    let actuationTime=300;

</script>

<style>
    div {
        left:0;
        top: 20%;
        position: absolute;
    }
</style>

<div>
    <center>
        <Typing />
    </center>
</div>