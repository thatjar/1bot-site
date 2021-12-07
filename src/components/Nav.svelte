<script>
  import { onMount } from "svelte";
  let showMobileMenu = false;

  const handleMobileIconClick = () => {
    showMobileMenu = !showMobileMenu;
  };

  const mediaQueryHandler = e => {
    if (!e.matches) {
      showMobileMenu = false;
    }
  };

  onMount(() => {
    const mediaQuery = window.matchMedia("(max-width: 768px)");
    mediaQuery.addListener(mediaQueryHandler);
  });
</script>

<nav>
  <div>
    <a href="/">
      <img src="/1bot.png" alt="Logo" height="50" />
    </a>
  </div>

  <div
    on:click={handleMobileIconClick}
    class={`mobile-icon${showMobileMenu ? " active" : ""}`}
  >
    <div class="middle-line" />
  </div>

  <div class={`navbar-list${showMobileMenu ? " active" : ""}`}>
    <a href="/">Home</a>
    <a href="/commands">Commands</a>
    <a href="https://top.gg/bot/884080176416309288/vote">Upvote</a>
    <a href="https://discord.gg/JGcnKxEPsW">Support Server</a>
    <a href="https://dsc.gg/1bot" class="add">Add 1Bot</a>
  </div>
</nav>
