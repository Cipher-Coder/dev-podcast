<script>
export let segment

</script>

<style>
  .menu {
    position: relative;
    margin-top: 25px;
    margin-right: 5px;
  }
  .menu-label {
    margin-left: 45px;
    font-weight: 600;
    color: #3f3f3f;
    text-shadow: 2px 2px 8px rgb(255, 251, 0);
  }

  .menu-list {
    margin-left: 45px;
  }

  img {
    margin-left: 5px;
  }

  .selected {
    position: relative;
    display: inline-block;
    color: #3f3f3f;
    text-shadow: 2px 2px 8px rgba(195, 0, 255, 0.65);
  }

  .selected:hover {
    color: #3f3f3f;
    text-shadow: 2px 2px 8px rgba(195, 0, 255, 0.65);
  }

  .selected::after {
    position: absolute;
    content: '';
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(195, 0, 255);
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    display: block;
    color: #9624c4;
  }

  a:hover {
    color: #ccb20c;
    background-color: #ffffff;
  } 

  .logo-img {
    max-height: 38px;
    max-width: 130px;
  }

  @media only screen and (max-width: 768px) {
    .menu {
      display: none;
    }
  }
</style>

<aside class="menu column">
  <a href=".">
    <img class="logo-img" src="img/newLogoSideWays.png" alt="RankCasts Logo" />
  </a>
  <p class="menu-label">General</p>
  <ul class="menu-list">
    <li>
      <a class:selected={segment === undefined} href=".">Home</a>
    </li>
    <li>
      <a class:selected={segment === 'about'} href="about">About</a>
    </li>
    <li>
      <a class:selected={segment === 'contact'} href="contact">Contact</a>
    </li>
  </ul>
  <p class="menu-label">Catagories</p>
  <ul class="menu-list">
    <li>
      <a class:selected={segment === 'general'} href="general">General</a>
    </li>
    <li>
      <a class:selected={segment === 'comedy'} href="comedy">Comedy</a>
    </li>
    <li>
      <a class:selected={segment === 'politics'} href="politics">Politics</a>
    </li>
    <li>
      <a class:selected={segment === 'developer'} href="developer">Developer</a>
    </li>
  </ul>
  <p class="menu-label">Transactions</p>
  <ul class="menu-list">
    <li>
      <a class:selected={segment === 'payments'} href="payments">Payments</a>
    </li>
    <li>
      <a class:selected={segment === 'transfers'} href="transfers">Transfers</a>
    </li>
    <li>
      <a class:selected={segment === 'balances'} href="balances">Balance</a>
    </li>
  </ul>
</aside>
