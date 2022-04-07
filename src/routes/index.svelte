<script context="module">
    export async function load({fetch}){
        const res = await fetch(
            `https://api.themoviedb.org/3/movie/popular?api_key=ba119c72f06e64c08f7e104f49c1699e&language=en-US&page=1`
        );
        const data = await res.json();
        // console.log(data.results)
        if(res.ok){
            return{
                props: {popular: data.results}
            }
        }
    }
</script>

<script>
    import PopularMovies from "../components/PopularMovies.svelte";
    export let popular;
</script>

<section>
    <PopularMovies {popular} />
</section>




