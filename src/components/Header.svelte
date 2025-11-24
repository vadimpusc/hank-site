<script>
  let isOpen = false;

  const toggleMenu = () => {
    isOpen = !isOpen;
  };

  const closeMenu = () => {
    isOpen = false;
  };
</script>

<header class="site-header">
  <div class="container header-inner">
    <a href="#home" class="logo">
      Hank<span>Orion</span>
    </a>

    <button
      class="nav-toggle"
      aria-label="Toggle navigation"
      on:click={toggleMenu}
    >
      <span></span>
      <span></span>
    </button>

    <nav class="nav" class:open={isOpen}>
      <a href="#home" class="nav-link" on:click={closeMenu}>Home</a>
      <a href="#about" class="nav-link" on:click={closeMenu}>About</a>
      <a
        href="https://shop.hankorion.com"
        class="nav-link"
        target="_blank"
        rel="noopener noreferrer"
        on:click={closeMenu}
      >
        Shop
      </a>
      <a href="#filmography" class="nav-link" on:click={closeMenu}>Filmography</a>
      <a href="#contact" class="nav-link" on:click={closeMenu}>Contact</a>
    </nav>
  </div>
</header>