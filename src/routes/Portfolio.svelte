<script lang="ts">
  const portfolioItems = [
    {
      title: "Studio Session - Jazz Ensemble",
      category: "Recording",
      image: "https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?auto=format&fit=crop&q=80&w=800",
      description: "Professional recording session with a 5-piece jazz ensemble."
    },
    {
      title: "Live Concert Production",
      category: "Live Sound",
      image: "https://images.unsplash.com/photo-1501612780327-45045538702b?auto=format&fit=crop&q=80&w=800",
      description: "Full production setup for a 2000-capacity venue concert."
    },
    {
      title: "Artist Development - Sarah James",
      category: "Development",
      image: "https://images.unsplash.com/photo-1516575334481-f85287c2c82d?auto=format&fit=crop&q=80&w=800",
      description: "Complete artist development program including vocal coaching and image consulting."
    },
    {
      title: "Hip-Hop Production",
      category: "Production",
      image: "https://images.unsplash.com/photo-1511379938547-c1f69419868d?auto=format&fit=crop&q=80&w=800",
      description: "Full album production for upcoming hip-hop artist."
    },
    {
      title: "Classical Recording",
      category: "Recording",
      image: "https://images.unsplash.com/photo-1520523839897-bd0b52f945a0?auto=format&fit=crop&q=80&w=800",
      description: "Studio recording of a classical string quartet."
    },
    {
      title: "Pop Vocal Production",
      category: "Production",
      image: "https://images.unsplash.com/photo-1621619856624-42fd193a0661?auto=format&fit=crop&q=80&w=800",
      description: "Vocal production and mixing for pop single release."
    }
  ];
</script>

<!-- Page Background -->
<div class="pt-24 min-h-screen" style="background: linear-gradient(to bottom, var(--color-light), var(--color-dark))">
  <div class="container mx-auto px-4">
    <h1 class="section-title">Our Portfolio</h1>
    
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
      {#each portfolioItems as item}
        <div class="card group overflow-hidden">
          <div class="relative aspect-video overflow-hidden">
            <img 
              src={item.image} 
              alt={item.title}
              class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
              <div class="absolute bottom-0 left-0 right-0 p-6 text-white transform translate-y-6 group-hover:translate-y-0 transition-transform duration-300">
                <span class="text-sm font-medium" style="color: var(--color-secondary)">{item.category}</span>
                <h3 class="text-xl font-bold">{item.title}</h3>
              </div>
            </div>
          </div>
          <div class="p-6">
            <p style="color: var(--color-dark)">{item.description}</p>
            <button class="mt-4 font-medium flex items-center gap-2" style="color: var(--color-primary)" on:mouseover={(e) => e.currentTarget.style.color = 'var(--color-secondary)'} on:mouseout={(e) => e.currentTarget.style.color = 'var(--color-primary)'}>
              View Details
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
              </svg>
            </button>
          </div>
        </div>
      {/each}
    </div>

    <!-- Call to Action -->
    <div class="card p-8 text-white text-center mb-16" style="background: linear-gradient(to right, var(--color-primary), var(--color-secondary))">
      <h2 class="text-2xl font-bold mb-4">Ready to Start Your Project?</h2>
      <p class="mb-8">Let's create something amazing together.</p>
      <a href="/contact" class="btn" style="background: white; color: var(--color-primary)">Get in Touch</a>
    </div>
  </div>
</div>
