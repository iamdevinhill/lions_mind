<script lang="ts">
  const currentYear = new Date().getFullYear();

  const socialLinks = [
    { icon: 'TikTok', label: 'TikTok', url: 'https://TikTok.com' },
    { icon: 'instagram', label: 'Instagram', url: 'https://instagram.com' },
    { icon: 'twitter', label: 'Twitter', url: 'https://twitter.com' },
    { icon: 'youtube', label: 'YouTube', url: 'https://youtube.com' }
  ];
</script>

<footer style="background-color: var(--color-light); border-top: 1px solid var(--color-light)">
  <!-- Accent Line -->
  <div style="height: 4px; background: linear-gradient(to right, var(--color-primary), var(--color-secondary))"></div>

  <div class="container mx-auto px-4 py-12">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
      <!-- Soundscape Info -->
      <div>
        <h3
          class="text-xl font-bold mb-4 bg-clip-text text-transparent"
          style="background-image: linear-gradient(to right, var(--color-primary), var(--color-secondary))"
        >
          Lions Mind Entertainment
        </h3>
        <p style="color: var(--color-dark)">
          Creating tomorrow's sound, today. Professional music production and artist development.
        </p>
      </div>

      <!-- Quick Links -->
      <div>
        <h4 class="text-lg font-semibold mb-4" style="color: var(--color-dark)">Quick Links</h4>
        <ul class="space-y-2">
          <li><a href="/services" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Services</a></li>
          <li><a href="/portfolio" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Portfolio</a></li>
          <li><a href="/about" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>About Us</a></li>
          <li><a href="/contact" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Contact</a></li>
        </ul>
      </div>

      <!-- Services -->
      <div>
        <h4 class="text-lg font-semibold mb-4" style="color: var(--color-dark)">Services</h4>
        <ul class="space-y-2">
          <li><a href="/services#production" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Music Production</a></li>
          <li><a href="/services#songwriting" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Songwriting</a></li>
          <li><a href="/services#mixing" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Mixing & Mastering</a></li>
          <li><a href="/services#development" class="transition-colors" style="color: var(--color-dark)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-primary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-dark)'}>Artist Development</a></li>
        </ul>
      </div>

      <!-- Contact & Socials -->
      <div>
        <h4 class="text-lg font-semibold mb-4" style="color: var(--color-dark)">Contact Us</h4>
        <ul class="space-y-2" style="color: var(--color-dark)">
          <li>123 Music Avenue</li>
          <li>Los Angeles, CA 90028</li>
          <li>contact@soundscapestudios.com</li>
          <li>(555) 123-4567</li>
        </ul>

        <!-- Social Icons -->
        <div class="flex space-x-4 mt-6">
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
      {#if social.icon.toLowerCase() === 'tiktok'}
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 448 512">
          <path d="M448,209.91a210.06,210.06,0,0,1-122.77-39.25V349.38A162.55,162.55,0,1,1,185,188.31V278.2a74.62,74.62,0,1,0,52.23,71.18V0l88,0a121.18,121.18,0,0,0,1.86,22.17h0A122.18,122.18,0,0,0,381,102.39a121.43,121.43,0,0,0,67,20.14Z"/>
        </svg>
      {:else if social.icon.toLowerCase() === 'instagram'}
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
          <path d="M7.75 2A5.75 5.75 0 0 0 2 7.75v8.5A5.75 5.75 0 0 0 7.75 22h8.5A5.75 5.75 0 0 0 22 16.25v-8.5A5.75 5.75 0 0 0 16.25 2h-8.5zm0 1.5h8.5A4.25 4.25 0 0 1 20.5 7.75v8.5a4.25 4.25 0 0 1-4.25 4.25h-8.5A4.25 4.25 0 0 1 3.5 16.25v-8.5A4.25 4.25 0 0 1 7.75 3.5zM12 7a5 5 0 1 0 0 10 5 5 0 0 0 0-10zm0 1.5a3.5 3.5 0 1 1 0 7 3.5 3.5 0 0 1 0-7zm5.25-.88a1.13 1.13 0 1 0 0 2.25a1.13 1.13 0 0 0 0-2.25z"/>
        </svg>
      {:else if social.icon.toLowerCase() === 'youtube'}
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
          <path d="M23.5 6.19a3.02 3.02 0 0 0-2.12-2.14C19.52 3.48 12 3.48 12 3.48s-7.51 0-9.38.57a3.02 3.02 0 0 0-2.12 2.14C0 8.07 0 12 0 12s0 3.93.5 5.81a3.02 3.02 0 0 0 2.12 2.14c1.87.57 9.38.57 9.38.57s7.51 0 9.38-.57a3.02 3.02 0 0 0 2.12-2.14C24 15.93 24 12 24 12s0-3.93-.5-5.81zM9.54 15.43V8.57l6.27 3.43-6.27 3.43z"/>
        </svg>
      {/if}
    </a>
  {/each}
        
        </div>
      </div>
    </div>

    <div class="mt-12 pt-8 text-center" style="color: var(--color-dark); border-top: 1px solid var(--color-light)">
      <p>&copy; {currentYear} Lions Mind Entertainment. All rights reserved.</p>
    </div>
  </div>
</footer>
