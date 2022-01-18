<script context="module">
  export async function load({ fetch }) {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts');
    const guides = await res.json();
    if (res.ok) {
      return {
        props: {
          guides,
        },
      };
    }
    return {
      status: res.status,
      error: new Error('Could not fetch the guides...'),
    };
  }
</script>

<script>
  import Component from '$lib/component.svelte';

  export let guides = [];

  let title = 'Guides Page';
</script>

<svelte:head>
  <title>Ninkit - Guides</title>
</svelte:head>

<Component {title}>
  <ul class="grid grid-cols-3 place-items-center gap-3 w-full py-5">
    {#each guides as guide (guide.id)}
      <li class="my-3">
        <a
          sveltekit:prefetch
          href={`/guides/${guide.id}`}
          class="border-2 border-dashed border-gray-300 hover:border-orange-600 hover:text-orange-500 w-full p-3 rounded shadow duration-300"
        >
          {guide.title.substring(0, 35)}
        </a>
      </li>
    {/each}
  </ul>
</Component>
