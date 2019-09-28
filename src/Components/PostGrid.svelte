<script>
  import PostGridItem from "./PostGridItem.svelte";
  export let posts;
</script>

<style>

</style>

<section>
  <div class="main main-raised">
    <div class="container">
      <h2 class="">Latest Blog Posts</h2>
      <br />
      <div class="row">

        {#each posts as post}
          <PostGridItem id={post.id} {...post} on:showdetails />
        {/each}
      </div>
    </div>
  </div>
</section>
