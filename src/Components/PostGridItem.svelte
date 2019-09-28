<script>
  import { createEventDispatcher } from "svelte";

  export let title;
  export let subtitle;
  export let imageBackdrop;
  export let id;

  let host = "http://localhost:1337";

  const dispatch = createEventDispatcher();
</script>

<style>

</style>

<div class="card card-blog">
  <div class="card-header card-header-image">
    <img
      class="img img-rounded img-raised"
      src={host + imageBackdrop.url}
      alt=""
      height="300" />
  </div>
  <div class="card-body">
    <h6 class="card-category text-info">Enterprise</h6>
    <h4 class="card-title">{title}</h4>
    <p class="card-description">{subtitle.slice(0, 200)}...</p>
    <button
      class="btn btn-primary"
      on:click={() => dispatch('showdetails', id)}>
      Read More
    </button>
  </div>
</div>
