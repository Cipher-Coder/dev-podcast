<script context="module">
  let current
</script>

<script>
  export let audioSrc
  let audio
  let paused = true

  function stopOthers() {
    if (current && current !== audio) current.pause()
    current = audio
  }
</script>

<style>
  audio {
    width: 75%;
    margin: 0.5em auto 1em auto;
    -webkit-transition: all 0.5s linear;
    -moz-transition: all 0.5s linear;
    -o-transition: all 0.5s linear;
    transition: all 0.5s linear;
    -moz-box-shadow: 2px 2px 4px 0px #9624c4;
    -webkit-box-shadow: 2px 2px 4px 0px #9624c4;
    box-shadow: 2px 2px 4px 0px#9624c4;
    -moz-border-radius: 90px;
    -webkit-border-radius: 90px;
    border-radius: 90px;
  }

  audio:focus {
    outline: 1px solid #eeecec;
  }

  audio:hover,
  audio:focus,
  audio:active {
    -webkit-box-shadow: 15px 15px 20px rgba(0, 0, 0, 0.4);
    -moz-box-shadow: 15px 15px 20px rgba(0, 0, 0, 0.4);
    box-shadow: 15px 15px 20px rgba(0, 0, 0, 0.4);
    -webkit-transform: scale(1.05);
    -moz-transform: scale(1.05);
    transform: scale(1.05);
  }

  .playing {
    color: red;
  }
</style>

<article class:playing={!paused}>
  <audio
    bind:this={audio}
    bind:paused
    on:play={stopOthers}
    src={audioSrc}
    preload="auto"
    controls />

</article>
