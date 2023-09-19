<script>
  import Skipnav from "../components/skipnav/skipnav.svelte";
  import Nav from "../components/nav/nav.svelte";
</script>

<Skipnav />
<Nav />

<main id="main">
  <slot />
</main>


<style>
main{
  width: calc(100% - 230px);
  height: 100vh;
  overflow: auto;
  background: #eaedf7;
  padding: 0 1.5rem;
}

</style>