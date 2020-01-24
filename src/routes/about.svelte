<script>

</script>

<style>
  .intro {
    margin: 45px 0;
  }

  .microphone {
    border-radius: 6px;
    -webkit-box-shadow: rgba(26, 26, 67, 0.05) 1px 1px 5px 0px,
      rgba(50, 50, 93, 0.5) -39px 62.5px 125px -25px,
      rgba(0, 0, 0, 0.3) 23.4px 37.5px 75px -37.5px;
    box-shadow: rgba(26, 26, 67, 0.05) 1px 1px 5px 0px,
      rgba(50, 50, 93, 0.5) -39px 62.5px 125px -25px,
      rgba(0, 0, 0, 0.3) 23.4px 37.5px 75px -37.5px;
  }

  h1 {
    font-size: 2rem;
    font-weight: bold;
  }

  h2 {
    font-size: 1.75rem;
    font-weight: bold;
    margin: 15px 0;
  }

  .writing {
    font-size: 1.1rem;
    line-height: 1.2rem;
  }

  .is-centered {
    text-align: center;
  }

  .projects {
    margin: 45px 0;
  }

  .devtabs {
    margin: auto;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
  }

  .devtabs-img {
    max-width: 800px;
    margin: auto;
    border-radius: 16px;
  }

  .caption {
    margin-left: 15px;
    font-size: 1.2rem;
  }
</style>

<svelte:head>
  <title>About | Top Podcasts</title>
</svelte:head>

<div class="container intro">
  <div class="columns">
    <div class="column">
      <img
        class="microphone"
        src="img/microphone1.jpg"
        alt="Professional microphone" />
    </div>
    <div class="column">
      <h1 class="is-centered">About Developer Podcasts</h1>
      <p class="writing">
        Podcasts have become a cultural phenomenon! They can inform, teach,
        entertain, and much much more! Everyone loves them, including me!
      </p>
      <p class="writing">
        The problem I encountered was there was no where I could go and just
        type in "Developer Podcasts" and find them. Not just find them but find
        the good ones. I searched and searched. Made my own list... but then I
        had to spend the time listeneing to every single one, just to find out
        which one was good. This has taken hours and I am still finding more and
        more that I want to try out.
      </p>
      <p class="writing">
        The solution... Developer Podcasts. Here you can submit podcasts that
        you like, have listened to, and enjoyed. The community can rank them so
        when anyone looks at the page they know immediately which podcasts are
        great.
      </p>
    </div>
  </div>
  <div class="container projects is-centered">
    <h2>Check out some of my other projects:</h2>
  </div>
  <div class="devtabs columns">
    <figure class="figure-container">
      <img
        class="devtabs-img column"
        src="img/devtabs.png"
        alt="Screenshot of Dev Tabs" />
      <figcaption class="caption">
        <a
          href="https://mattaz.com/devtabs"
          target="_blank"
          rel="noopener noreferrer">
          Dev Tabs Browser Extension
        </a>
      </figcaption>
    </figure>

  </div>

</div>
