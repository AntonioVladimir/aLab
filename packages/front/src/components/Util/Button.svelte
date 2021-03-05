<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  const submit = () => {
    dispatch("submit", {});
  };
</script>

<button class="btn btn-success text-center btn-block px-5" on:click={submit}>Search</button>
