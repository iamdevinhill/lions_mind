<script lang="ts"> 
  import { Link } from "svelte-routing";
  import { fade, fly } from 'svelte/transition';
  let isMenuOpen = false;

  const closeMenu = () => {
    isMenuOpen = false;
  };

  const socialLinks = [
    { icon: "tiktok", url: "https://tiktok.com", label: "TikTok" },
    { icon: "instagram", url: "https://instagram.com", label: "Instagram" },
    { icon: "youtube", url: "https://youtube.com", label: "YouTube" }
  ];
</script>

<!-- Accent Line -->
<div style="height: 4px; background: linear-gradient(to right, var(--color-primary), var(--color-secondary))"></div>

<header class="fixed w-full z-50 backdrop-blur-md shadow-lg" style="background-color: rgba(255,255,255,0.9)">
  <div class="container mx-auto px-4 py-6">
    <nav class="flex items-center justify-between">
      <!-- Brand Link with smaller text -->
      <Link to="/" class="text-2xl flex items-center group z-50 relative">
        <span style="background-image: linear-gradient(to right, var(--color-primary), var(--color-secondary));" class="bg-clip-text text-transparent">
          Lions Mind
        </span>
        <span class="ml-2 transition-colors group-hover:text-[var(--color-primary)]" style="color: var(--color-dark)">
          Entertainment
        </span>
      </Link>

      <!-- Desktop Navigation + Social Icons -->
      <div class="hidden md:flex items-center space-x-8">
        <!-- Navigation links with reduced text size -->
        <Link to="/" class="nav-link text-lg">Home</Link>
        <Link to="/services" class="nav-link text-lg">Services</Link>
        <Link to="/portfolio" class="nav-link text-lg">Portfolio</Link>
        <Link to="/about" class="nav-link text-lg">About</Link>
        <Link to="/contact" class="nav-link text-lg">Contact</Link>

        <!-- Social Media Icons (desktop) with smaller SVGs -->
        <div class="flex space-x-4 pl-4">
          {#each socialLinks as social}
            <a
              href={social.url}
              target="_blank"
              rel="noopener noreferrer"
              aria-label={social.label}
              class="transition-colors duration-300"
              style="color: var(--color-dark)"
              on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-secondary)'}
              on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}
            >
              {@html social.icon.toLowerCase() === 'tiktok'
                ? `<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 448 512">
                     <path d="M448,209.91a210.06,210.06,0,0,1-122.77-39.25V349.38A162.55,162.55,0,1,1,185,188.31V278.2a74.62,74.62,0,1,0,52.23,71.18V0l88,0a121.18,121.18,0,0,0,1.86,22.17h0A122.18,122.18,0,0,0,381,102.39a121.43,121.43,0,0,0,67,20.14Z"/>
                   </svg>`
                : social.icon.toLowerCase() === 'instagram'
                ? `<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                     <path d="M7.75 2A5.75 5.75 0 0 0 2 7.75v8.5A5.75 5.75 0 0 0 7.75 22h8.5A5.75 5.75 0 0 0 22 16.25v-8.5A5.75 5.75 0 0 0 16.25 2h-8.5zm0 1.5h8.5A4.25 4.25 0 0 1 20.5 7.75v8.5a4.25 4.25 0 0 1-4.25 4.25h-8.5A4.25 4.25 0 0 1 3.5 16.25v-8.5A4.25 4.25 0 0 1 7.75 3.5zM12 7a5 5 0 1 0 0 10 5 5 0 0 0 0-10zm0 1.5a3.5 3.5 0 1 1 0 7 3.5 3.5 0 0 1 0-7zm5.25-.88a1.13 1.13 0 1 0 0 2.25 1.13 1.13 0 0 0 0-2.25z"/>
                   </svg>`
                : social.icon.toLowerCase() === 'youtube'
                ? `<svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                     <path d="M23.5 6.19a3.02 3.02 0 0 0-2.12-2.14C19.52 3.48 12 3.48 12 3.48s-7.51 0-9.38.57a3.02 3.02 0 0 0-2.12 2.14C0 8.07 0 12 0 12s0 3.93.5 5.81a3.02 3.02 0 0 0 2.12 2.14c1.87.57 9.38.57 9.38.57s7.51 0 9.38-.57a3.02 3.02 0 0 0 2.12-2.14C24 15.93 24 12 24 12s0-3.93-.5-5.81zM9.54 15.43V8.57l6.27 3.43-6.27 3.43z"/>
                   </svg>`
                : ``
              }
            </a>
          {/each}
        </div>
      </div>

      <!-- Mobile Menu Toggle with Animation - Visible only on mobile -->
      <div class="md:hidden">
        <button
          class="hamburger-menu p-2 z-50 relative"
          on:click={() => isMenuOpen = !isMenuOpen}
          aria-label="Toggle menu"
        >
          <div class="hamburger-icon" class:open={isMenuOpen}>
            <span></span>
            <span></span>
            <span></span>
          </div>
        </button>
      </div>
    </nav>
  </div>
</header>

<!-- Mobile Menu (positioned outside header for better z-index handling) -->
{#if isMenuOpen}
  <div 
    transition:fade={{ duration: 200 }}
    class="fixed inset-0 z-40 md:hidden overflow-y-auto"
    style="background: linear-gradient(to bottom right, var(--color-primary), var(--color-secondary)); padding-top: 80px;"
  >
    <div class="flex flex-col items-center justify-between h-full py-16">
      <div class="flex flex-col items-center space-y-8">
        {#each ['Home', 'Services', 'Portfolio', 'About', 'Contact'] as page, i}
          <Link 
            to={page === 'Home' ? '/' : `/${page.toLowerCase()}`}
            class="mobile-nav-link text-3xl font-bold"
            style="color: var(--color-light)"
            on:click={closeMenu}
          >
            <span in:fly={{ y: 20, delay: i * 50, duration: 200 }}>
              {page}
            </span>
          </Link>
        {/each}
      </div>

      <!-- Mobile Socials with corrected icons -->
      <div 
        class="flex space-x-8 mt-12"
        in:fly={{ y: 20, delay: 500, duration: 300 }}
      >
        {#each socialLinks as social}
          <a 
            href={social.url}
            target="_blank"
            rel="noopener noreferrer"
            class="transition-colors duration-300"
            style="color: var(--color-light)"
            on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-dark)'}
            on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-light)'}
            aria-label={social.label}
          >
            {@html social.icon.toLowerCase() === 'tiktok'
              ? `<svg class="w-7 h-7" fill="currentColor" viewBox="0 0 448 512">
                   <path d="M448,209.91a210.06,210.06,0,0,1-122.77-39.25V349.38A162.55,162.55,0,1,1,185,188.31V278.2a74.62,74.62,0,1,0,52.23,71.18V0l88,0a121.18,121.18,0,0,0,1.86,22.17h0A122.18,122.18,0,0,0,381,102.39a121.43,121.43,0,0,0,67,20.14Z"/>
                 </svg>`
              : social.icon.toLowerCase() === 'instagram'
              ? `<svg class="w-7 h-7" fill="currentColor" viewBox="0 0 24 24">
                   <path d="M7.75 2A5.75 5.75 0 0 0 2 7.75v8.5A5.75 5.75 0 0 0 7.75 22h8.5A5.75 5.75 0 0 0 22 16.25v-8.5A5.75 5.75 0 0 0 16.25 2h-8.5zm0 1.5h8.5A4.25 4.25 0 0 1 20.5 7.75v8.5a4.25 4.25 0 0 1-4.25 4.25h-8.5A4.25 4.25 0 0 1 3.5 16.25v-8.5A4.25 4.25 0 0 1 7.75 3.5zM12 7a5 5 0 1 0 0 10 5 5 0 0 0 0-10zm0 1.5a3.5 3.5 0 1 1 0 7 3.5 3.5 0 0 1 0-7zm5.25-.88a1.13 1.13 0 1 0 0 2.25 1.13 1.13 0 0 0 0-2.25z"/>
                 </svg>`
              : social.icon.toLowerCase() === 'youtube'
              ? `<svg class="w-7 h-7" fill="currentColor" viewBox="0 0 24 24">
                   <path d="M23.5 6.19a3.02 3.02 0 0 0-2.12-2.14C19.52 3.48 12 3.48 12 3.48s-7.51 0-9.38.57a3.02 3.02 0 0 0-2.12 2.14C0 8.07 0 12 0 12s0 3.93.5 5.81a3.02 3.02 0 0 0 2.12 2.14c1.87.57 9.38.57 9.38.57s7.51 0 9.38-.57a3.02 3.02 0 0 0 2.12-2.14C24 15.93 24 12 24 12s0-3.93-.5-5.81zM9.54 15.43V8.57l6.27 3.43-6.27 3.43z"/>
                 </svg>`
              : ``
            }
          </a>
        {/each}
      </div>
    </div>
  </div>
{/if}

<style>
  .nav-link {
    position: relative;
    color: var(--color-dark);
    transition: color 0.3s;
  }
  .nav-link:hover {
    color: var(--color-primary);
  }
  .nav-link::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--color-primary);
    transition: width 0.3s;
  }
  .nav-link:hover::after {
    width: 100%;
  }
  .mobile-nav-link {
    position: relative;
    overflow: hidden;
    padding-bottom: 4px;
  }
  .mobile-nav-link::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--color-light);
    transition: width 0.5s;
  }
  .mobile-nav-link:hover::after {
    width: 100%;
  }
  /* Hamburger Menu Animation */
  .hamburger-menu {
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition-property: opacity, filter;
    transition-duration: 0.15s;
    height: 44px;
    width: 44px;
  }
  .hamburger-icon {
    position: relative;
    width: 24px;
    height: 20px;
  }
  .hamburger-icon span {
    position: absolute;
    height: 2px;
    width: 100%;
    background-color: var(--color-dark);
    border-radius: 4px;
    transition: all 0.3s ease-in-out;
    left: 0;
  }
  .hamburger-icon span:nth-child(1) {
    top: 0;
  }
  .hamburger-icon span:nth-child(2) {
    top: 9px;
  }
  .hamburger-icon span:nth-child(3) {
    bottom: 0;
  }
  /* X Animation */
  .hamburger-icon.open span:nth-child(1) {
    transform: translateY(9px) rotate(45deg);
  }
  .hamburger-icon.open span:nth-child(2) {
    opacity: 0;
    transform: translateX(20px);
    width: 0;
  }
  .hamburger-icon.open span:nth-child(3) {
    transform: translateY(-9px) rotate(-45deg);
  }
  /* Ensure buttons are easily tappable on mobile */
  @media (max-width: 768px) {
    button, a {
      min-height: 44px;
      min-width: 44px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .mobile-nav-link {
      margin: 8px 0;
    }
  }
</style>
