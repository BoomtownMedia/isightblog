<script>
  import { createEventDispatcher, onMount } from "svelte";
  let host = "https://blog-api-isight.herokuapp.com";

  export let title;
  export let subtitle;
  export let postBody;
  export let id;
  export let posts;
  export let imageBackdrop;

  onMount(() => {
    window.scrollTo(0, 0);
  });

  const dispatch = createEventDispatcher();
  const selectedPost = posts.find(i => i.id === id);
  const imageUrl = host + selectedPost.imageBackdrop.url;
</script>

<style>

</style>

<div
  class="page-header header-filter"
  data-parallax="true"
  style="background-image: url('{imageUrl}')">
  <div class="container">
    <div class="row">
      <div class="col-md-8 ml-auto mr-auto text-center">
        <h1 class="title">{selectedPost.title}</h1>
        <h4>{selectedPost.subtitle}</h4>
        <br />
        <a href="#blog" class="btn btn-rose btn-round btn-lg">
          <i class="material-icons">format_align_left</i>
          Read Article
        </a>
      </div>
    </div>
  </div>
</div>
<div class="main main-raised" id="blog">
  <div class="container">
    <div class="section section-text">
      <div class="row">
        <div class="col-md-8 ml-auto mr-auto">
          <h3 class="title">{selectedPost.subtitle}</h3>
          <p>{selectedPost.postBody}</p>
        </div>
      </div>
    </div>
  </div>
</div>
