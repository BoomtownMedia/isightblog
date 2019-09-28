<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
</script>

<nav
  class="navbar navbar-color-on-scroll navbar-transparent fixed-top
  navbar-expand-lg "
  color-on-scroll="100"
  id="sectionsNav">
  <div class="container">
    <div class="navbar-translate">
      <a class="navbar-brand" href="#home">
        <img
          src="logo.png"
          style="width: 110px"
          alt="Blue/Black Aviator Wings ISight Logo" />
      </a>
      <a
        class="navbar-brand navbar-left"
        href="#home"
        style="font-weight: bolder">
        ISIGHT RPV Services
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        aria-expanded="false"
        aria-label="Toggle navigation">
        <span class="sr-only">Toggle navigation</span>
        <span class="navbar-toggler-icon" />
        <span class="navbar-toggler-icon" />
        <span class="navbar-toggler-icon" />
      </button>
    </div>
    <button
      class="btn btn-large btn-success"
      on:click={() => dispatch('showoverview')}>
      Home
    </button>
  </div>
</nav>
