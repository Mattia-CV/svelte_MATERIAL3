<script lang="ts">
  import NavRail from "./NavRail.svelte";
  import Footer from "./Footer.svelte";
</script>

<div class="shell">
  <NavRail />

  <section class="main">
    <div class="content">
      <div class="container">
        <slot />
      </div>
    </div>
    <Footer />
  </section>
</div>

<style>
  .shell {
    display: grid;
    grid-template-columns: var(--nav-width) 1fr;
    min-height: 100dvh;
  }

  .main {
    display: flex;
    flex-direction: column;
    min-height: 100dvh;
  }

  .content {
    flex: 1;
    padding: 18px;
  }

  .container {
    max-width: var(--content-max);
  }
</style>
