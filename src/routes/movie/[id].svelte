<script context="module">
    export async function load({fetch, params}){
        console.log(params.id)
        const res = await fetch(`https://api.themoviedb.org/3/movie/${[params.id]}?api_key=${import.meta.env.VITA_API}&language=en-US`);
        const movieDatail = await res.json();
        console.log(movieDatail)
        if(res.ok){
            return {
                props: { movieDatail }
            }
        }
    }
</script>

<script>
    export let movieDatail;
</script>

<div class="movie-details">
    <div class="img-container">
        <img src={'https://image.tmdb.org/t/p/original'+movieDatail.backdrop_path} alt={movieDatail.backdrop_path}>
    </div>
    <div class="txt-container">
        <h1>{movieDatail.title}</h1>
        <p class="overview">{movieDatail.overview}</p>
        <p><span>Release Date</span></p>
        {movieDatail.release_date}<br/>
        <span></span>
    </div>
</div>