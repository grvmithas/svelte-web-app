<!-- <script>
  import Prism from "svelte-prism";
</script>

<svelte:head>
  <link
    href="
https://cdn.jsdelivr.net/npm/prismjs@1.29.0/themes/prism.min.css
"
    rel="stylesheet"
  />
</svelte:head>

<section>
  <h1 class="main-content-title">mule initializr</h1>

  <div class="input-group">
    <input
      class="form-control input-group-form"
      placeholder="Search Exchange"
      type="text"
    />
    <button class="input-group-text">
      <i />
    </button>
  </div>

  <Prism language="javascript">
    {`
     
    "name": "John Doe",
    "email": "john.doe@example.com",
    "age": 30
  
    `}
  </Prism>
</section> -->

<script>
  import Prism from "prismjs";
  let code = ` {
	"name": "John Doe",
  "email": "john.doe@example.com",
  "age": 30
	}`;

  let language = "javascript";
</script>

<section>
  <h1 class="main-content-title">mule initializr</h1>
  <div class="input-group">
    <input
      class="form-control input-group-form"
      placeholder="Search Exchange"
      type="text"
    />
    <button class="input-group-text">
      <i />
    </button>
  </div>
  <div class="code">
    {@html Prism.highlight(code, Prism.languages[language])}
  </div>

  <div>
    <button>
      
    </button>
  </div>


</section>


<svelte:head>
  <link
    href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.22.0/themes/prism.min.css"
    rel="stylesheet"
  />
</svelte:head>

<style>
  .code {
    white-space: pre-wrap;
    background: #0e0e23;
  }

</style>
