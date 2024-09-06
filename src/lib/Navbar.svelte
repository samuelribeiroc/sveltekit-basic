<script>
  import { page } from "$app/stores";

  const items = [
    { href: "/", label: "Home" },
    { href: "/about", label: "About" },
    { href: "/contact", label: "Contact" },
    { href: "/portfolio", label: "Portfolio" }
  ]
</script>

<nav class="bg-white shadow dark:bg-gray-800">
  <div class="container flex items-center justify-center p-6 mx-auto text-gray-600 capitalize dark:text-gray-300">
    <a href="/">
      <img src="favicon.png" alt="logo" class="mr-5" />
    </a>
    
    {#each items as {href, label}}
      {#if href === $page.url.pathname}
        <a href={href} class="text-gray-800 transition-colors duration-300 transform dark:text-gray-200 border-b-2 border-blue-500 mx-1.5 sm:mx-6">
          {label}
        </a>
      {:else}
        <a {href} class="border-b-2 border-transparent hover:text-gray-800 transition-colors duration-300 transform dark:hover:text-gray-200 hover:border-blue-500 mx-1.5 sm:mx-6">
          {label}
        </a>
      {/if}
    {/each}
  </div>
</nav>

<style>
  img {
    height: 2rem;
  }
</style>