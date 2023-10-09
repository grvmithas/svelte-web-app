
<script>
  import Skipnav from "../components/skipnav/skipnav.svelte";
  import Nav from "../components/nav/nav.svelte";
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
  <style>
    @import 'src/styles/icons.css'; /* Adjust the path based on your project structure */
    @import 'src/styles/global.css'; 
  </style>
</svelte:head>


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
  padding:1.5rem;
}

</style>