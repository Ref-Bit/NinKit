<script>
  import Component from '$lib/component.svelte';

  let title = 'Get in touch!';
  let text =
    'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque ipsum quisquam ipsa saepe harum corporis, sed corrupti voluptatum vitae quaerat natus laborum nemo est. Quam esse reprehenderit iure soluta eius?';
</script>

<svelte:head>
  <title>Ninkit - Contact Us</title>
</svelte:head>

<Component {title} {text} />
