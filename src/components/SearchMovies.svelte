<script>
    let inputValue = '';
    let active = false;

    function cancelInactive() {
        if(inputValue){
            active = true;
        } else {
            active = false;
        }
    }
</script>

<form action="">
    {#if !active}
        <label for="search_movie">Search Movie</label>
    {/if}
    <input 
        on:blur={() => (active = false)}
        on:focus={() => (active = true)}
        bind:value = {inputValue}
        name="search_movie"
        type="text"
    />
    {#if inputValue}
        <button>Search</button>
    {/if}
</form>