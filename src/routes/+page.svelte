<script>
    let textareaContent = ""; // This variable will hold the content of the textarea
  
    const handleTextAreaHeight = (textarea) => {
      textarea.style.height = "auto";
      textarea.style.height = textarea.scrollHeight + "px";
    };
  
    const handleTextareHeight = (event) => {
      if (event.key === "Enter") {
        handleTextAreaHeight(event.target);
      }
    };
  
    async function postPSChat() {
      try {
        const response = await fetch("https://api.psnext.info/api/chat", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            title: "Svelte Post Example",
            body: "This is an example of a POST request in Svelte.",
            userId: 1,
          }),
        });
  
        const data = await response.json();
        console.log("Data posted successfully:", data);
      } catch (error) {
        console.error("Error posting data:", error);
      }
    }
  
    const handleSubmit = (event) => {
      event.preventDefault();
      console.log("I am submit");
      console.log(textareaContent);
      postPSChat();
    };
  </script>
  
  <section>
    <h1 class="main-content-title">PS Chat</h1>
  
    <div class="chat">
      <p>Content: {textareaContent}</p>
    </div>
    
    <div class="chat__bottom">
      <form class="search-form" on:submit={handleSubmit}>
        <textarea
          bind:value={textareaContent}
          placeholder="Type something..."
          class="search-form__text form-control"
          on:keydown={handleTextareHeight}
        />
        <button class="search-form__button btn" type="submit">
          <i class="icon-paper-plane" />
        </button>
      </form>
    </div>
  
  </section>
  
  
  
  
  <style>
    .search-form__button {
      width: 2rem;
      height: 2rem;
      position: absolute;
      right: 0.75rem;
      bottom: 0.75rem;
      background: #6259ca;
      border: none;
      color: #ffffff;
      cursor: pointer;
    }
  
    .input-group {
      position: relative;
      display: flex;
      flex-wrap: wrap;
      align-items: stretch;
      width: 100%;
    }
    .input-group__button {
      position: absolute;
      right: 0;
    }
    .input-group__text {
      padding-right: 10px;
      position: relative;
      flex: 1 1 auto;
      width: 1%;
      min-width: 0;
    }
    .chat__bottom {
      width: 100%;
      position: absolute;
      bottom: 0;
      background: #eaedf7;
      padding: 2rem;
      z-index: 9;
    }
    .search-form {
      max-width: 48rem;
      margin-left: auto;
      margin-right: auto;
      position: relative;
      box-shadow: 0 0 transparent, 0 0 transparent, 0 0 15px rgba(0, 0, 0, 0.25);
      border-radius: 0.75rem;
      margin-bottom: 2rem;
    }
    .form-control {
      display: block;
      width: 100%;
      padding: 0.375rem 0.75rem;
      font-size: 1rem;
      line-height: 1.5;
      color: #495057;
      background-color: #fff;
      background-clip: padding-box;
      border: 1px solid #ced4da;
      border-radius: 0.75rem;
      transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
      font-family: "Roboto", sans-serif;
    }
    .search-form__text {
      overflow: auto;
      max-height: 200px;
      height: 58px;
      resize: none;
      padding: 1rem 48px 1rem 1rem;
    }
  </style>
  