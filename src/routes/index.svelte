<script>
  import { onMount } from 'svelte'
  const URL =
    'https://v2-api.sheety.co/0b5f365fe37e4932db5dabe9775b63d0/podcastList/developer'
  let posts = []

  onMount(async function() {
    const res = await fetch(URL)
    const json = await res.json()
    posts = json['developer']
  })
</script>

<style>
  h1 {
    font-size: 2rem;
    font-weight: bold;
    margin: 25px 20px;
  }

  h3 {
    font-size: 1.25rem;
    margin: 20px 10px;
  }

  .focus-in-expand {
    animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
    -webkit-animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94)
      both;
  }

  @keyframes focus-in-expand {
    0% {
      letter-spacing: -0.5em;
      -webkit-filter: blur(12px);
      filter: blur(12px);
      opacity: 0;
    }
    100% {
      -webkit-filter: blur(0px);
      filter: blur(0px);
      opacity: 1;
    }
  }
</style>

<svelte:head>
  <title>Home | Top Podcasts</title>
</svelte:head>

<div class="column">
  <h1 class="focus-in-expand">Rank The Best Developer Podcasts:</h1>
  {#each posts as post}
    <div class="column">
      <div class="card">
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <figure class="image is48x48">
                <img src={post.image} alt="Album Cover" />
              </figure>

            </div>
          </div>
          <div class="media-content">
            <p class="title is-5">{post.name}</p>
          </div>
        </div>
      </div>
    </div>
  {:else}
    <p>No posts</p>
  {/each}
  <h3>More to Come!!!</h3>
</div>
