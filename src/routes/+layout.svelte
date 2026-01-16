<script lang="ts">
  import "../app.css";
  import "$lib/material"; // <- registers md-* elements
  import AppShell from "$lib/components/AppShell.svelte";
</script>

<AppShell>
  <slot />
</AppShell>
