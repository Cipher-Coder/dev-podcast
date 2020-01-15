<style>
  h1,
  figure,
  p {
    text-align: center;
    margin: 0 auto;
  }

  h1 {
    font-size: 2.8em;
    text-transform: uppercase;
    font-weight: 700;
    margin: 0 0 0.5em 0;
  }

  figure {
    margin: 0 0 1em 0;
  }

  img {
    width: 100%;
    margin: 0 0 1em 0;
  }

  .logo-pic {
    max-width: 600px;
    margin-top: -20px;
  }

  .main-pic {
    max-width: 580px;
  }

  p {
    margin: 1em auto;
  }

  .container {
    text-align: center;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 2.8em;
    }
  }
</style>

<svelte:head>
  <title>Developer Podcasts</title>
</svelte:head>
<div>
  <div class="container">
    <img alt="Logo" src="img/cover.png" class="logo-pic" />
    <h1>Rank Your Favorite Developer Podcast!</h1>
  </div>
  <div class="container">
    <figure>
      <img alt="Audio Studio" src="img/studio.jpg" class="main-pic" />
      <figcaption>Podcasting Studio</figcaption>
    </figure>
    <p>
      <strong>
        Try editing this file (src/routes/index.svelte) to test live reloading.
      </strong>
    </p>
  </div>
  <div class="columns">
    <div class="column">This is a column!!!!</div>
    <div class="column" />
    This is a column 2!!!!
  </div>

</div>
