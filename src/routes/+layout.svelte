<script>
  import {page, navigating} from "$app/stores";
</script>

<nav>
  <a href="/" aria-current={$page.url.pathname === "/"}>Home</a>
  <a href="/about" aria-current={$page.url.pathname === "/about"}>about</a>
  <a href="/pschat" aria-current={$page.url.pathname === "/pschat"}>PSchat</a>
</nav>

<slot />
