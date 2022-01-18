<script>
  export let title;
  export let text;
</script>

<section class="component min-h-screen">
  <h1>{title}</h1>
  {#if text}
    <p>{text}</p>
  {/if}
  <slot />
</section>
