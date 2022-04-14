<script>
    let count = 0;

    function incrementBtn() {
        count += 1;
    }
</script>

<h1>Number: {count}</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<a href="/about">hihi</a>
<button on:click={incrementBtn}>Increment</button>
<style>
    p {
        font-size: 2rem;
    }
</style>