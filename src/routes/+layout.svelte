<!-- __layout.svelte -->
<script>
	import { Nav, Footer } from "$lib/components"
    import { dev } from '$app/environment';
    import { injectAnalytics } from '@vercel/analytics/sveltekit';
 
    injectAnalytics({ mode: dev ? 'development' : 'production' });
</script>

<main>
    <Nav /> <!-- adds the nav (small and large) -->
  
    <slot />
<a href="https://www.dynastydads.com/" class="floatingHome">
  Home
</a>

<style>
  .floatingHome {
    position: fixed;
    bottom: 20px;
    right: 20px;
    padding: 0.6rem 1rem;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    backdrop-filter: blur(6px);
    background: rgba(255, 255, 255, 0.15); /* light on dark */
    color: white;
    border: 1px solid rgba(255, 255, 255, 0.25);
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
    z-index: 9999;
    transition: background 0.2s ease, transform 0.2s ease;
  }

  .floatingHome:hover {
    background: rgba(255, 255, 255, 0.25);
    transform: translateY(-2px);
  }

  @media (prefers-color-scheme: light) {
    .floatingHome {
      background: rgba(0, 0, 0, 0.1); /* dark on light */
      color: black;
      border: 1px solid rgba(0, 0, 0, 0.2);
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }

    .floatingHome:hover {
      background: rgba(0, 0, 0, 0.2);
    }
  }
</style>
    <Footer /> <!-- adds the footer -->
</main>
