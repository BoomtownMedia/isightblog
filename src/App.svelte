<script>
  import Strapi from "strapi-sdk-javascript/build/main";
  import { onMount } from "svelte";

  import Navbar from "./Components/Navbar.svelte";
  import Header from "./Components/Header.svelte";
  import PostGrid from "./Components/PostGrid.svelte";
  import Footer from "./Components/Footer.svelte";
  import PostDetail from "./Components/PostDetail.svelte";

  let page = "overview";
  let pageData = {};
  let posts = [];

  onMount(async function() {
    const response = await fetch("https://blog-api-isight.herokuapp.com/posts");
    posts = await response.json();
  });

  function showDetails(event) {
    page = "details";
    pageData.id = event.detail;
  }
  function showOverview(event) {
    page = "overview";
    console.log("overview");
  }
</script>

<style>

</style>

<Navbar on:showoverview={showOverview} />
{#if page === 'overview'}
  <Header />
  <PostGrid {posts} on:showdetails={showDetails} />
  <Footer />
{:else}
  <PostDetail id={pageData.id} {posts} />
{/if}
