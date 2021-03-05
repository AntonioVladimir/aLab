<script>
  export let type;
</script>


<div class="col-md-2 col-xs-1 mx-auto my-1 text-light ">
  <div class="form-check">
    <input
      class="form-check-input"
      type="checkbox"
      value="tv"
      id="flexCheckDefault"
      bind:group={type}
    />
    <label class="form-check-label" for="tv"> Tv </label>
  </div>
</div>
<div class="col-md-2 col-xs-1 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="checkbox"
      value="ova"
      id="flexCheckChecked"
      bind:group={type}
    />
    <label class="form-check-label" for="ova"> Ova </label>
  </div>
</div>
<div class="col-md-2 col-xs-1 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="checkbox"
      value="movie"
      id="flexCheckChecked"
      bind:group={type}
    />
    <label class="form-check-label" for="movie"> Movies </label>
  </div>
</div>
<div class="col-md-2 col-xs-1 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="checkbox"
      value="special"
      id="flexCheckChecked"
      bind:group={type}
    />
    <label class="form-check-label" for="special"> Specials </label>
  </div>
</div>
<div class="col-md-2 col-xs-1 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="checkbox"
      value="ona"
      id="flexCheckChecked"
      bind:group={type}
    />
    <label class="form-check-label" for="ona"> Ona </label>
  </div>
</div>

