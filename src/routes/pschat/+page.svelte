<script>
  let textareaContent = ""; // This variable will hold the content of the textarea
</script>

<form>
  <div class="input-group">
    <textarea bind:value="{textareaContent}" placeholder="Type something..." class="input-group__text"></textarea>
    <button class="input-group__button">sa as</button>
  </div>
  
</form>



<style>
  .input-group{
    position: relative;
    display: flex;
    flex-wrap: wrap;
    align-items: stretch;
    width: 100%;
  }
  .input-group__button{
    position: absolute;
    right: 0;
  }
  .input-group__text{
    padding-right: 10px;
    position: relative;
    flex: 1 1 auto;
    width: 1%;
    min-width: 0;
  }
</style>



<p>Content: {textareaContent}</p>