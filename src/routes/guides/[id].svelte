<script context="module">
  export async function load({ fetch, page }) {
    const res = await fetch(
      `https://jsonplaceholder.typicode.com/posts/${page.params.id}`
    );
    const guide = await res.json();
    if (res.ok) {
      return {
        props: {
          guide,
        },
      };
    }
    return {
      status: 301,
      // error: new Error('Could not fetch the guides...'),
      redirect: '/guides',
    };
  }
</script>

<script>
  import Component from '$lib/component.svelte';
  export let guide;
</script>

<Component title={guide.title} text={guide.body} />
