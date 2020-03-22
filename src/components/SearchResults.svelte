<script>
  export let artist
  export let title
  export let feedURL
</script>

<style>
  li {
    margin-bottom: 10px;
  }
  .artist-name {
    color: #5c5b5b;
  }

  .podcast-name {
    font-size: 1.1rem;
    font-weight: bold;
  }

  .feedURL {
    color: #5c5b5b;
  }
</style>

<li>
  <p class="podcast-name">{title}</p>
  <p class="artist-name">By: {artist}</p>
  <p class="feedURL">URL: {feedURL}</p>
</li>
