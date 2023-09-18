<script>
  import Skipnav from "../components/skipnav/skipnav.svelte";
  import Nav from "../components/nav/nav.svelte";
</script>

<Skipnav />
<Nav />
<main id="main">
  <slot />
</main>
