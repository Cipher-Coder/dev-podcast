<script>
  import { onMount } from 'svelte'
  import Nav from '../components/Nav.svelte'
  import Footer from '../components/Footer.svelte'
  import Sidebar from '../components/Sidebar.svelte'

  export let segment
  let showNavbar = false
  const mediaQueryHandler = e => {
    if (e.matches) {
      showNavbar = false
    } else {
      showNavbar = true
    }
  }

  onMount(() => {
    const mediaListener = window.matchMedia('(min-width: 767px)')
    mediaListener.addListener(mediaQueryHandler)
  })
</script>

<style>
  /* main {
    position: relative;
    background-color: white;
    margin-left: 10rem;
    box-sizing: border-box;
    min-width: 40%;
  }

  @media (max-width: 767px) {
    main {
      margin: 7px;
    }
  } */
</style>

<div class="columns">
  {#if showNavbar != false}
    <Nav {segment} />
  {:else}
    <Sidebar />
  {/if}
  <slot />
</div>

<Footer />
