<script context="module">
  export const load = async ({ page }) => ({
    props: {
      key: page.path,
    },
  });
</script>

<script>
  import Nav from "../components/Nav.svelte";
  import PageTransition from "../components/PageTransition.svelte";

  export let key;
</script>

<Nav />

<main class="main-content">
  <PageTransition refresh={key}>
    <slot />
  </PageTransition>

  <footer>
    <h1 class="config">LINKS</h1>

    <div>
      <a href="/commands">Command List</a>
      <a href="https://top.gg/bot/884080176416309288/vote">Upvote</a>
      <a href="https://discord.gg/JGcnKxEPsW">Support Server</a>
      <a href="https://github.com/opensourze/1bot">GitHub</a>
    </div>
  </footer>
</main>
