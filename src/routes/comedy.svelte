<script>
  import { onMount } from 'svelte'
  import PodCard from '../components/PodCard.svelte'
  import VoteButton from '../components/VoteButton.svelte'
  import SubmitForm from '../components/SubmitForm.svelte'
  import PodSearch from '../components/PodSearch.svelte'
  import AudioPlayer from '../components/AudioPlayer.svelte'

  const URL = 'https://v2-api.sheety.co/0b5f365fe37e4932db5dabe9775b63d0/podcastList/comedy'
  let posts = []

  onMount(async function() {
    const res = await fetch(URL)
    const json = await res.json()
    posts = json['comedy']
  })

</script>

<style>
h1 {
    font-size: 2rem;
    font-weight: bold;
    margin: 25px 20px;
    text-align: center;
  }

  h3 {
    font-size: 1.15rem;
    margin: 20px 10px;
  }

  .sorry-msg {
    font-size: 1.2rem;
    color: orangered;
  }

  .focus-in-expand {
    animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
    -webkit-animation: focus-in-expand 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94)
      both;
  }

  @-webkit-keyframes focus-in-expand {
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

  .is-right {
    float: right;
    padding-left: 75px;
  }
</style>

<svelte:head>
  <title>Comedy | RankCasts</title>
</svelte:head>

<div class="container">

  <h1 class="focus-in-expand">Rank The Best Comedy Podcasts:</h1>
  <div class="container">
    <div class="column is-one-third is-right">
      <div class="row">
        <SubmitForm />
      </div>
      <div class="row">
        <PodSearch />
      </div>
    </div>
    {#each posts as post}
      <PodCard src={post.image} name={post.name} alt={post.name}>
        <span slot="audio">
          <AudioPlayer audioSrc="./data/sample.mp3" />
        </span>
        <span slot="vote">
          <VoteButton count={post.likes} />
        </span>
      </PodCard>
    {:else}
      <p class="sorry-msg">
        Sorry... No Podcasts to display! Please add one with the Submit form!
      </p>
    {/each}

  </div>

  <h3>
    Your favorite podcast not here? Use the Submit form at the top and see what
    others think about your favs!!
  </h3>

</div>