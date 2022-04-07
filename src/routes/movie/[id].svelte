<script context="module">
    export async function load({fetch, params}){
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/${params.id}?api_key=ba119c72f06e64c08f7e104f49c1699e&language=en-US`
        );
        const movieDetail = await res.json();
        // console.log(data.results)
        if(res.ok){
            return{
                props: {movieDetail}
            }
        }
    }
</script>

<script>
    export let movieDetail
</script>


<div class="movie-detials">
    <div class="img-container">
        <img src={`https://image.tmdb.org/t/p/w500${movieDetail.poster_path}`} alt={movieDetail.title}>
    </div>
    <div class="txt-container">
        <h1>{movieDetail.title}</h1>
    </div>
</div>