<script>
  export let segment;
</script>

<nav>
  <ul>
    <li>
      <a aria-current={segment === undefined ? "border" : undefined} href="."
        >home
        <span /></a
      >
    </li>
    <li>
      <a aria-current={segment === "about" ? "border" : undefined} href="about"
        >about
        <span /></a
      >
    </li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li>
      <a
        rel="prefetch"
        aria-current={segment === "blog" ? "border" : undefined}
        href="blog"
        >blog
        <span /></a
      >
    </li>
  </ul>
</nav>

<style>
  nav,
  ul,
  li {
    display: flex;
    justify-content: center;
  }

  nav {
    margin: 3em 0;
  }

  li:not(:last-child) {
    display: flex;
    list-style-type: none;
    padding: 0;
    margin-right: 1.5em;
  }

  a {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: Georgia, serif;
    font-size: 1.6em;
    color: #000;
    text-decoration: none;
  }

  span {
    background: #ff4500 none repeat scroll 0 0;
    height: 3px;
    border-radius: 25px;
    width: 0%;
  }

  a[aria-current="border"] span {
    animation: expand 0.5s forwards;
  }

  @keyframes expand {
    100% {
      width: 125%;
    }
  }
</style>
