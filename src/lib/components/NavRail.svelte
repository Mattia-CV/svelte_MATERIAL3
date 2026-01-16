<script lang="ts">
  import { page } from "$app/stores";

  const isCurrent = (href: string) => $page.url.pathname === href;
</script>

<aside class="rail">
  <div class="top">
    <md-icon-button aria-label="Menu">
      <span class="material-symbols-outlined">menu</span>
    </md-icon-button>
  </div>

  <md-list>
    <md-list-item
      type="link"
      href="/"
      class:current={isCurrent("/")}
      aria-current={isCurrent("/") ? "page" : undefined}
    >
      <span slot="start" class="material-symbols-outlined">home</span>
      Home
    </md-list-item>

    <md-list-item
      type="link"
      href="/page1"
      class:current={isCurrent("/page1")}
      aria-current={isCurrent("/page1") ? "page" : undefined}
    >
      <span slot="start" class="material-symbols-outlined">description</span>
      Page 1
    </md-list-item>

    <md-list-item
      type="link"
      href="/contacts"
      class:current={isCurrent("/contacts")}
      aria-current={isCurrent("/contacts") ? "page" : undefined}
    >
      <span slot="start" class="material-symbols-outlined">contacts</span>
      Contacts
    </md-list-item>
  </md-list>
</aside>

<style>
  .rail {
    position: sticky;
    top: 0;
    height: 100dvh;
    padding: 12px 10px;
    background: var(--md-sys-color-surface-container-high);
    border-right: 1px solid rgba(0, 0, 0, 0.08);
  }

  .top {
    display: flex;
    justify-content: center;
    margin-bottom: 10px;
  }

  /* “Selected” styling via tokens (works well with Material Web lists) */
  md-list-item.current {
    --md-list-item-label-text-color: var(--md-sys-color-primary);
    --md-list-item-leading-icon-color: var(--md-sys-color-primary);
    /* this token may exist depending on version; harmless if ignored */
    --md-list-item-container-color: rgba(103, 80, 164, 0.12);
    border-radius: 18px;
  }
</style>
