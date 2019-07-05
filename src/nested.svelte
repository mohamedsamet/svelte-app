<script>
    import { writable } from 'svelte/store';
    function handleClick() {
        console.log('click')
    }
    export let abc = 'test';
</script>
<p>...don't affect this element {@html abc}</p>
<button on:click={handleClick}>test</button>