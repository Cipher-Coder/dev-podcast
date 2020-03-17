<script>
  import { onMount } from 'svelte'

  export let segment

  onMount(() => {
    const navbarBurgers = Array.prototype.slice.call(
      document.querySelectorAll('.navbar-burger'),
      0
    )

    if (navbarBurgers.length > 0) {
      navbarBurgers.forEach(el => {
        el.addEventListener('click', () => {
          const target = el.dataset.target
          const target2 = document.getElementById(target)

          el.classList.toggle('is-active')
          target2.classList.toggle('is-active')
        })
      })
    }
  })
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 600;
    padding: 0 1em;
  }

  .navbar-brand {
    padding-top: 10px;
  }

  .selected {
    position: relative;
    display: inline-block;
    color: #19d1b2;
  }

  .selected:hover {
    color: #19d1b2;
  }

  .selected::after {
    position: absolute;
    content: '';
    width: calc(100% - 1em);
    height: 2px;
    background-color: #19d1b2;
    display: block;
    bottom: -1px;
  }

  @media only screen and (min-width: 1024px) {
    .navbar-burger {
      display: none;
    }
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
    color: #000;
  }

  a:hover {
    color: gray;
  }
</style>

<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href=".">
      <img src="img/newLogoSideWays.png" alt="Logo" />
    </a>
    <span
      role="button"
      class="navbar-burger"
      aria-label="menu"
      aria-expanded="false"
      data-target="navMenu">
      <span aria-hidden="true" />
      <span aria-hidden="true" />
      <span aria-hidden="true" />
    </span>
  </div>
  <div id="navMenu" class="navbar-menu">
    <div class="navbar-start">
      <a class:selected={segment === undefined} href=".">Home</a>
      <a class:selected={segment === 'about'} href="about">About</a>
      <a rel="prefetch" class:selected={segment === 'blog'} href="blog">Blog</a>
    </div>
    <div class="navbar-end" />
  </div>
</nav>
