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
    margin: 0 0 1em 0;
  }

  .main-pic {
    max-width: 580px;
  }

  .audio-column {
    text-align: center;
    margin: auto;
  }

  audio {
    margin: auto;
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
    <div class="column audio-column">
      <img
        src="https://is4-ssl.mzstatic.com/image/thumb/Music113/v4/60/4e/d6/604ed6ba-6a5a-5faa-edf5-189a290f3aa3/source/100x100bb.jpg"
        alt="Podcast Photo" />
      <audio controls>
        <source
          src="https://traffic.libsyn.com/syntax/Syntax214.mp3"
          type="audio/mpeg" />
        Your browser does not support the audio tag.
      </audio>
    </div>
    <div class="column" />
    This is a column 2!!!!
  </div>

</div>
