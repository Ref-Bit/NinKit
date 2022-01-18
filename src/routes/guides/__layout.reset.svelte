<script>
  import '../../app.css';
  import Footer from '../../components/Footer.svelte';
  import Header from '../../components/Header.svelte';
</script>

<main
  class="container bg-gray-100 dark:bg-gray-900 text-gray-900 dark:text-gray-50 font-body"
>
  <Header />
  <slot />
  <Footer />
</main>
