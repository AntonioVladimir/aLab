<script>
  export let rated;
</script>

<div class="col-md-2 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="radio"
      name="exampleRadios"
      id="exampleRadios1"
      value="option1"
      bind:group={rated}
    />
    <label class="form-check-label" for="exampleRadios1"> Friendly </label>
  </div>
</div>
<div class="col-md-2 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="radio"
      name="exampleRadios"
      id="exampleRadios2"
      value="option2"
      bind:group={rated}
    />
    <label class="form-check-label" for="exampleRadios2"> Children </label>
  </div>
</div>
<div class="col-md-2 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="radio"
      name="exampleRadios"
      id="exampleRadios3"
      value="option3"
      bind:group={rated}
    />
    <label class="form-check-label" for="exampleRadios3"> Teens </label>
  </div>
</div>
<div class="col-md-2 text-light mx-auto my-1">
  <div class="form-check">
    <input
      class="form-check-input"
      type="radio"
      name="exampleRadios"
      id="exampleRadios4"
      value="option4"
      bind:group={rated}
    />
    <label class="form-check-label" for="exampleRadios4"> Adult </label>
  </div>
</div>
