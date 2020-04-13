<script>
  import { onMount } from 'svelte'
  import Nav from '../components/Nav.svelte'
  import Footer from '../components/Footer.svelte'
  import Sidebar from '../components/Sidebar.svelte'

  export let segment
  let showNavbar = false

</script>

<style>
@media only screen and (max-width: 768px) {
    :global(.sidebar) {
      display: none;
    }
  }

  @media only screen and (min-width: 767px) {
    :global(.navbar) {
      display: none;
    }
  }

</style>

<div class="columns"> 
  <div class="top-nav">
    <Nav {segment} />
  </div>
  <div class="side-nav is-1">
    <Sidebar {segment}/>
  </div>
  <slot />
</div>
<Footer />
