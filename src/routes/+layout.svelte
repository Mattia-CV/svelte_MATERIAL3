<script lang="ts">
  import "../app.css";
  import "$lib/material"; // <- registers md-* elements
  import AppShell from "$lib/components/AppShell.svelte";
  import { isLoggedIn } from "$lib/stores/session";
  import FakePage from "$lib/components/FakePage.svelte";
</script>

{#if $isLoggedIn}
  <AppShell>
    <slot />
  </AppShell>
{:else}
  <FakePage />
{/if}
