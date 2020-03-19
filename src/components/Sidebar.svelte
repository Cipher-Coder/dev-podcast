<script>

</script>

<style>
  .sidebar {
    margin-top: 25px;
    margin-right: 5px;
  }
  .menu-label {
    margin-left: 45px;
    font-weight: 600;
    color: #ccb20c;
  }

  .menu-list {
    margin-left: 45px;
  }

  img {
    margin-left: 5px;
  }

  .menu-list :global(a) {
    color: #9624c4;
  }

  .menu-list :global(a:hover) {
    text-decoration: none;
    color: #ccb20c;
  }

  .logo-img {
    min-height: 38px;
    min-width: 130px;
  }

  @media only screen and (max-width: 768px) {
    .sidebar {
      display: none;
    }
  }
</style>

<div class="column sidebar is-1">
  <aside class="menu">
    <a href=".">
      <img
        class="logo-img"
        src="img/newLogoSideWays.png"
        alt="RankCasts Logo" />
    </a>
    <p class="menu-label">Catagories</p>
    <ul class="menu-list">
      <li>
        <a href=".">General</a>
      </li>
      <li>
        <a href="comedy">Comedy</a>
      </li>
      <li>
        <a href="politics">Politics</a>
      </li>
      <li>
        <a href="/">Developer</a>
      </li>
    </ul>
    <p class="menu-label">General</p>
    <ul class="menu-list">
      <li>
        <a href=".">Home</a>
      </li>
      <li>
        <a href="about">About</a>
      </li>
      <li>
        <a href="contact">Contact</a>
      </li>
    </ul>
    <p class="menu-label">Transactions</p>
    <ul class="menu-list">
      <li>
        <a href=".">Payments</a>
      </li>
      <li>
        <a href=".">Transfers</a>
      </li>
      <li>
        <a href=".">Balance</a>
      </li>
    </ul>
  </aside>

</div>
