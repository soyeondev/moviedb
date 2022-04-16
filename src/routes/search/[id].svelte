<script context="module">
    export async function load({fetch, params }){
        const res = await fetch(`https://api.themoviedb.org/3/search/movie?api_key=${import.meta.env.VITA_API}&language=en-US&query=${params.id}&page=1&include`);
        const data = await res.json();
        if(res.ok){
            return {
                props: { searchedMovie: data.results}
            }
        }
    }

    
</script>