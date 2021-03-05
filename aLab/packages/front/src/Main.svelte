<script>
  import axios from "axios";

  import AgeSelector from "./components/Util/AgeSelector.svelte";
  import Button from "./components/Util/Button.svelte";
  import Pagination from "./components/Util/Pagination.svelte";
  import Search from "./components/Util/Search.svelte";
  import Types from "./components/Util/Types.svelte";

  import AnimeRender from "./components/AnimeRender.svelte";

  let nameS = "";
  let type = [];
  let rated = "";
  let response = [];
  let animeList = [];
  let show = false;
  let start;
  let end;
  let page = 1;
  let pageNum = 1;

  $: start = (page - 1) * 4;
  $: end = page * 4;

  const sumbitSearch = async () => {
    show = false;
    let url = "https://api.jikan.moe/v3/search/anime";
    let params = {};
    params.limit = 40;
    if (nameS === "") {
      alert("Please search something!");
    } else {
      params.q = nameS;
    }
    if (type.length !== 0) {
      if (type.length === 1) {
        params.type = type[0];
      } else {
        params.type = type.reduce((a, b) => `${a}/${b}`);
      }
    }
    if (rated !== "") {
      params.rated = rated;
    }

    response = await axios.request({
      url: url,
      params: params,
      method: "GET",
    });
    animeList = response.data.results;
    pageNum = Math.floor(animeList.length / 4);
    show = true;
  };
  const goPrev = () => {
    if (page === 1) {
    } else {
      page = page - 1;
    }
  };
  const goNe = () => {
    if (page >= pageNum) {
    } else {
      page = page + 1;
    }
  };
</script>

<div class="container mt-5">
    <h2 class="text-center mb-5 mt-5">Shearch your favourite Anime</h2>
  <div class="row mt-5">
    
    <div class="col-xl-10 col-md-9 col-sm-8 mt-1"><Search bind:nameS /></div>
    <div class="col-xl-2 col-md-3 col-sm-4 mt-1">
      <Button on:submit={sumbitSearch} />
    </div>
  </div>
  <div class="row mb-5">
    <div class="col-xl-6 col-md-12 col-sm-12 col-xs-1">
      <div class="container mt-4">
        <h3 class="text-center mb-4 ">Age Selector</h3>
        <div class="row bg-dark py-2">
          <AgeSelector bind:rated />
        </div>
      </div>
    </div>
    <div class="col-xl-6 col-md-12 col-sm-12 col-xs-6">
      <div class="container mt-4">
        <h3 class="text-center mb-4">Type Selector</h3>
        <div class="row bg-dark py-2">
          <Types bind:type />
        </div>
      </div>
    </div>
  </div>
  <div class="row">
      
  <AnimeRender bind:animeList bind:start bind:end />

</div>
  <div class="row">
    <div class="col my-5 d-flex align-items-center justify-content-center">
        <Pagination {show} bind:pageNum bind:page on:prev={goPrev} on:next={goNe} />
    </div>
  </div>
  
</div>
