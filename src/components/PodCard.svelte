<script>
  export let src
  export let name
  export let alt
</script>

<style>
  .media-right {
    float: right;
    margin-top: -70px;
    margin-right: 45px;
  }

  .card {
    border-radius: 6px;
  }
</style>

<div class="column is-three-fifths s6">
  <div class="card">
    <div class="card-content">
      <div class="media">

        <div class="media-left">
          <figure class="image is48x48">
            <img {src} {alt} />
          </figure>
        </div>
        <div class="audio-player column">
          <slot name="audio" />
        </div>
      </div>
      <div class="media-content">
        <p class="title is-5">{name}</p>
      </div>
      <div class="media-right">
        <slot name="vote" />
      </div>
    </div>
  </div>
</div>
