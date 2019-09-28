<script>
  import { createEventDispatcher } from "svelte";

  export let title;
  export let subtitle;
  export let imageBackdrop;
  export let id;
  export let category;

  let host = "https://blog-api-isight.herokuapp.com";
  let imageUrl = host + imageBackdrop.url;

  const dispatch = createEventDispatcher();
</script>

<style>

</style>

<div class="col-md-6">
  <div
    class="card card-raised card-background"
    style="background-image: url('{imageUrl}')">
    <div class="card-body">
      <h6 class="card-category text-info">{category}</h6>
      <h4 class="card-title">{title}</h4>
      <p class="card-description">{subtitle.slice(0, 200)}...</p>
      <button
        class="btn btn-primary btn-round"
        on:click={() => dispatch('showdetails', id)}>
        Read Article
      </button>
    </div>
  </div>
</div>
