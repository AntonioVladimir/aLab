<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let show;
  export let pageNum;
  export let page;
  let activate = "bg-green-300 text-white";
  let deactivateHover = "";
  let deactivate = "bg-green-200 text-gray-400";
  let activateHover = " hover:bg-white hover:text-green-400";
  const goPrevious = () => {
    dispatch("prev");
  };
  const goNext = () => {
    dispatch("next");
  };
</script>

{#if show}
  
    <button
      class="btn btn-dark text-light mx-1 {page === 1
        ? deactivate
        : activate}  {page === 1
        ? deactivateHover
        : activateHover} "
      on:click={goPrevious}> &lt; Previous</button
    >
    <button
      class="btn btn-dark text-light mx-1 {page === pageNum
        ? deactivate
        : activate}  {page ===
      pageNum
        ? deactivate
        : activate}"
      on:click={goNext}>Next &gt;</button
    >

  
{/if}
