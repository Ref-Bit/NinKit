<script context="module">
  /** @type {import('@sveltejs/kit').ErrorLoad} */
  export function load({ error, status }) {
    return {
      props: { error, status },
    };
  }
</script>

<script>
  import Component from '$lib/component.svelte';

  export let status;
  export let error;
</script>


<svelte:head>
  <title>Ninkit - {status} Error</title>
</svelte:head>

<Component title={status} text={error.message}>
  <a href="/guides">
    <button
      class="inline-flex items-center bg-orange-600 text-gray-50 border-0 py-2 px-3 shadow focus:outline-none hover:bg-gray-500 rounded font-title text-xl mt-4 md:mt-0 duration-300"
      >View all guides
      <svg
        fill="none"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        class="w-4 h-4 ml-1"
        viewBox="0 0 24 24"
      >
        <path d="M5 12h14M12 5l7 7-7 7" />
      </svg>
    </button>
  </a>
</Component>
