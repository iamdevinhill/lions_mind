
<script>
  import { onMount } from 'svelte';
  
  let currentImageIndex = 0;
  const images = ['/lion.png'];
  
  onMount(() => {
    const interval = setInterval(() => {
      currentImageIndex = (currentImageIndex + 1) % images.length;
    }, 5000);
    
    return () => clearInterval(interval);
  });
  </script>
  
  <div class="min-h-screen" style="background: linear-gradient(to bottom, var(--color-light), var(--color-light))">
    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0 z-0">
        {#each images as image, i}
        <img 
          src={image} 
          alt="Studio atmosphere" 
          class="absolute inset-0 transform scale-80 w-full h-full object-cover transition-opacity duration-1000"
          style="opacity: {i === currentImageIndex ? '1' : '0'}"
        />
      {/each}
      
        <!-- Semi-transparent overlay to ensure text readability -->
      </div>
      
      <div class="container relative z-20 text-center px-4">
        <div class="float-animation">
          <h1 class="text-5xl md:text-7xl font-bold mb-6 bg-clip-text text-transparent" 
              style="background-image: linear-gradient(to right, var(--color-primary), var(--color-light))">
            Create. Produce. Inspire.
          </h1>
        </div>
        <p class="text-xl md:text-2xl mb-8 max-w-3xl mx-auto text-white">
          Where Vision Meets Sound | Professional Music Production Studio
        </p>
        <div class="flex flex-col sm:flex-row justify-center gap-4 items-center">
          {#each [
            { href: "/contact", label: "Book a Session" },
            { href: "/portfolio", label: "Our Work" }
          ] as btn}
            <a
            href={btn.href}
            class="btn w-full sm:w-auto text-white shadow-lg transition-all duration-300 transform hover:scale-105 px-6 py-3 rounded-lg"
            style="background-color: var(--color-dark)"
            on:mouseout={(e) => e.currentTarget.style.backgroundColor = 'var(--color-dark)'}
            on:blur={(e) => e.currentTarget.style.backgroundColor = 'var(--color-dark)'}
            >
            {btn.label}
            </a>

          {/each}
        </div>
      </div>
    </section>

  <!-- Services Preview -->
  <section class="py-20">
    <div class="container">
      <h2 class="section-title">Our Services</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        {#each ['Music Production', 'Songwriting', 'Mixing & Mastering', 'Artist Development'] as service}
          <div class="card p-6 group hover:-translate-y-2">
            <h3 class="text-xl font-semibold mb-4 transition-colors group-hover:text-[var(--color-primary)]">{service}</h3>
            <p style="color: var(--color-dark)">Professional {service.toLowerCase()} services tailored to your needs.</p>
          </div>
        {/each}
      </div>
    </div>
  </section>


  <!-- Testimonials -->
  <section class="py-20">
    <div class="container">
      <h2 class="section-title">What Our Clients Say</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each Array(3) as _, i}
          <div class="card p-8 hover:bg-gradient-to-br hover:from-[var(--color-primary)]/5 hover:to-[var(--color-secondary)]/5">
            <div class="text-4xl mb-4" style="color: var(--color-secondary)">"</div>
            <p class="mb-6" style="color: var(--color-dark)">
              Amazing experience working with the team. They brought my vision to life and exceeded all expectations.
            </p>
            <div class="flex items-center">
              <div class="w-12 h-12 rounded-full flex items-center justify-center text-white font-bold text-xl"
                   style="background: linear-gradient(to right, var(--color-primary), var(--color-secondary))">
                {String.fromCharCode(65 + i)}
              </div>
              <div class="ml-4">
                <h4 class="font-semibold" style="color: var(--color-dark)">Client Name</h4>
                <p style="color: var(--color-dark)">Artist</p>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
</div>
