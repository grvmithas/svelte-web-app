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
  "age": 30,
	}`;

  let language = "javascript";
</script>

<section>
  <h1 class="main-content-title">mule initializr</h1>
  <div class="setting-wrap">
    <div class="card mule__card">
      <div class="card__body">
        <div class="form-group">
          <div class="input-group">
            <input
              class="form-control input-group-form"
              placeholder="Search Exchange"
              type="text"
            />
            <button class="input-group-text">
              <i class="icon-search" />
            </button>
          </div>
        </div>

        <div class="form-group">
          <label for="muleprojeectname">Mulesoft Project Name</label>
          <input type="text" class="form-control" />
        </div>
        <div class="form-group">
          <label for="muleprojectversion">Version</label>
          <input type="text" class="form-control" id="muleprojectversion" />
        </div>
        <button class="btn btn-primary btn-block"> Generate </button>
      </div>
    </div>
    <div class="card mule__card">
      <div class="card__body">
        <div class="code">
          <div class="code-title">Generated code</div>
          {@html Prism.highlight(code, Prism.languages[language])}
        </div>
      </div>
    </div>
  </div>

  <div />
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
  .mule__card{
    margin-bottom: 1.5rem;
  }
</style>
