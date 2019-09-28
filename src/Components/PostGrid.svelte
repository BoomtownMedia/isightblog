<script>
  import PostGridItem from "./PostGridItem.svelte";
  export let posts;
</script>

<style>

</style>

<section>
  <div class="main main-raised">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2 class="">Latest Blog Posts</h2>
          <br />
          <div class="card-columns">
            {#each posts as post}
              <PostGridItem id={post.id} {...post} on:showdetails />
            {/each}
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
