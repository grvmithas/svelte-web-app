<script>
  import { onMount } from "svelte";

  let bearer_token = "";
  let displayStoredToken = "";
  let error = "";
  onMount(() => {
    const storedBearerTokenValue = localStorage.getItem("pschatuser");
    if (storedBearerTokenValue !== null) {
      displayStoredToken = storedBearerTokenValue;
    } else {
      displayStoredToken = "Please Set Token"
    }
  });

  const setBearerTokenInLocalStorage = () => {
    if (bearer_token.trim() === "") {
      error = "Input cannot be empty.";
      return;
    }
    localStorage.setItem("pschatuser", bearer_token);
  };
</script>

<section class="">
  <h1 class="main-content-title">Settings</h1>
  <div class="setting-wrap">
    <div class="card setting-wrap__card">
      <div class="card__body">
        <h5 class="card__body-title">Current Bearer Token</h5>
        {displayStoredToken}
        {#if displayStoredToken == ""}
        <div>Please Enter The Token</div>
      {/if}
      </div>
    </div>

    <div class="card setting-wrap__card">
      <div class="card__body">
        <h5 class="card__body-title">Change Bearer Token</h5>
        <textarea class="form-control" rows="3" bind:value={bearer_token} />
        <!-- {error && <div>{error}</div>} -->
        {#if error !== ""}
          <div style="color: red;">{error}</div>
        {/if}
      </div>
    </div>
    <button
      class="btn btn-primary btn-block"
      on:click={setBearerTokenInLocalStorage}
    >
      Save Changes
    </button>
  </div>
</section>
