<script>
  import { onMount } from 'svelte'
  import Nav from '../components/Nav.svelte'
  import Footer from '../components/Footer.svelte'
  import Sidebar from '../components/Sidebar.svelte'

  export let segment
  let showNavbar = false

  onMount(() => {
    const mediaListener = window.matchMedia('(max-width: 767px)')
    mediaListener.addEventListener('change', e => {
      showNavbar = e.matches
    })
  })
</script>

<style>

</style>

<div class="columns">
  {#if showNavbar !== false}
  <div class="top-nav">
    <Nav {segment} />
  </div>
  {:else}
  <div class="side-nav is-1">
    <Sidebar />
  </div>
  {/if}
  <slot />
</div>
<Footer />
