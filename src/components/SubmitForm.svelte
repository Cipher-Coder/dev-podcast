<script>
  export let error_boolean = false

  async function handleSubmit(event) {
    console.log(event)
    console.log(event.target)
    console.log(event.target.podcastName.value)
    console.log(event.target.podcastUrl.value)
    // Hide Submit Button After Submission
    document.getElementById('submitButton').style.display = 'none'
    // Show thank you after submission
    let thanks = document.createElement('P')
    thanks.textContent = 'Thank you for your submission'
    document.getElementById('submission').appendChild(thanks)
    // Clear submit inputs
    event.target.podcastName.value = ''
    event.target.podcastUrl.value = ''
  }

  function validateForm(e) {
    let textbox = event.target
    error_boolean = false
    if (textbox.value === '') {
      textbox.setCustomValidity('Podcast URL Required!!')
    } else if (textbox.validity.typeMismatch) {
      error_boolean = true
      textbox.setCustomValidity('Please enter a valid URL')
    } else {
      textbox.setCustomValidity('')
    }
    return true
  }
</script>

<style>
  article {
    margin-bottom: 35px;
  }
  .form-error {
    font-size: 0.9rem;
    color: red;
    margin-bottom: 5px;
    margin-top: -5px;
  }

  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }

  button {
    background-color: #9624c4;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
    font-weight: normal;
  }

  button:hover {
    background-color: #712391e1;
    border: 1px solid transparent;
    color: #fff;
    font-size: 1rem;
  }

  input:focus {
    outline: 1px solid rgb(167, 167, 167);
  }
</style>

<article class="container">
  <h2 class="submit-title">Submit An Awesome Podcast!</h2>
  <form
    id="podcast-submission"
    class="submit-podcast"
    on:submit|preventDefault={handleSubmit}
    on:invalid={validateForm}
    on:changed={validateForm}
    on:input={validateForm}>
    <label for="podcastName">Podcast Name:</label>
    <input required type="text" id="podcastName" />
    <label for="podcastUrl">Podcast Feed URL</label>
    <input required type="url" id="podcastUrl" />
    <br />
    {#if error_boolean}
      <p class="form-error">Format: https://example.com</p>
    {/if}
    <div id="submission">
      <button id="submitButton" class="button" type="submit">Submit</button>
    </div>

  </form>

</article>
