<script>
  export let name;
  export let imageURL;
  export let episodes;
  export let score;
  export let synopsis;
</script>

<div class="card mb-4 w-100 border-0 shadow">
  <div class="card-header bg-dark">
    <h5 class="text-light text-center text-capitalize ">{name}</h5>
  </div>
  <div class="row g-0">
    <div class="col-xl-3 col-md-3 col-sm-0 col-xs-10">
      <img src={imageURL} alt="anime cover" class="img-fluid w-100" />
    </div>
    <div class="col-xl-9 col-md-9 col-sm-12 col-xs-2 pr-5">
      <div class="card-body">
        <h4 class="card-title text-primary">Synopsis:</h4>
        <p class="card-text">{synopsis}</p>
        <p class="card-text h5">
            <span class=" text-warning h5">Episodes: </span>{episodes}
          </p>
        <div class="row">
          <div class="col text-right">
            
            <p class="card-text h5 mt-3">
              <span class=" h5 text-info">Score: </span>{score}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
