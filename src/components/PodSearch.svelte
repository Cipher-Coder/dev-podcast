<script>
  import SearchResults from '../components/SearchResults.svelte'
  let searchParam = ''
  let baseurl = `https://itunes.apple.com`
  let url
  let result
  let searchResult = []

  async function searchForPodcast() {
    let searchTerm = searchParam
    let query = `/search?term=${searchTerm}&entity=podcast`
    url = encodeURI(baseurl + query)

    try {
      let response = await fetch(url)
      let data = await response.json()
      searchResult = data['results']
      console.log('Success: ', data)
    } catch (err) {
      console.log('Error: ', err)
    }
  }

  function submissionHandler(e) {
    result = searchForPodcast()
    searchParam = ''
  }
</script>

<style>
  .submit-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }

  h4 {
    font-size: 1.2rem;
    font-weight: bold;
    margin-bottom: 10px;
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

  ol {
    list-style-type: square;
  }
</style>

<article class="column">
  <h2 class="submit-title">Search for Podcast</h2>
  <form on:submit|preventDefault={submissionHandler}>
    <label for="name">Search:</label>
    <input bind:value={searchParam} id="search" type="text" />
    <br />
    <button type="submit" class="button" id="searchbutton">Search</button>
  </form>
  <div>
    {#if result === undefined}
      <p>Search for: {searchParam}</p>
    {:else}
      {#await result}
        <p>Loading...</p>

      {:then results}
        <h4>Results:</h4>
        <ol>
          {#each searchResult as searchResults}
            <SearchResults
              artist={searchResults.artistName}
              title={searchResults.collectionName}
              feedURL={searchResults.feedUrl} />
          {/each}
        </ol>
      {:catch error}
        <p>{error.message}</p>

      {/await}
    {/if}

  </div>

</article>
