<script>
  export let count = 0
  let url = ''

  function handleVote() {
    count += 1
  }
</script>

<style>
  .voting {
    text-align: center;
  }
  button {
    border: none;
  }

  button:hover {
    border: none;
  }

  button:active {
    background-color: #fff;
    border: none;
  }

  .ranking-p {
    color: #3a3a3a;
  }
</style>

<div class="voting">
  <button on:click={handleVote} class="upvote-btn button">&#128077;</button>
  <p class="ranking-p">Upvotes: {count}</p>
</div>
