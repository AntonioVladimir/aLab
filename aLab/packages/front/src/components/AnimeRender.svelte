<script>
  import Card from "./Util/Card.svelte";
  export let animeList;
  export let start = 0;
  export let end = 4;
  $: console.log(start);
  $: showList = animeList.slice(start, end);
</script>


    
    {#each showList as anime (anime.mal_id)}
    <div class="col-xl-12">
      <Card
        name={anime.title}
        imageURL={anime.image_url}
        score={anime.score}
        episodes={anime.episodes}
        synopsis={anime.synopsis}
      />
    </div>
    {/each}

