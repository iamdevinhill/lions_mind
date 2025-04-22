<script lang="ts">
  interface Service {
    title: string;
    description: string;
    features: string[];
  }

  const services: Service[] = [
    {
      title: 'Music Production',
      description: 'State-of-the-art music production services with industry-standard equipment and experienced producers.',
      features: ['Professional Recording', 'Arrangement', 'Sound Design', 'Vocal Production']
    },
    {
      title: 'Songwriting',
      description: 'Collaborative songwriting sessions with our team of experienced writers and producers.',
      features: ['Melody Writing', 'Lyrics Development', 'Song Structure', 'Genre Expertise']
    },
    {
      title: 'Mixing & Mastering',
      description: 'Professional mixing and mastering services to give your music the perfect finish.',
      features: ['Audio Mixing', 'Mastering', 'Stem Mixing', 'Quality Control']
    },
    {
      title: 'Artist Development',
      description: 'Comprehensive artist development program to help you reach your full potential.',
      features: ['Brand Development', 'Performance Training', 'Career Strategy', 'Marketing Plan']
    }
  ];
</script>

<div class="pt-24 min-h-screen" style="background: linear-gradient(to bottom, var(--color-light), var(--color-dark))">
  <div class="container">
    <h1 class="section-title">Our Services</h1>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-20">
      {#each services as service}
        <div class="card group p-8">
          <h2 class="text-2xl font-bold mb-4 transition-colors group-hover:text-[var(--color-primary)]">
            {service.title}
          </h2>
          <p class="mb-6" style="color: var(--color-dark)">{service.description}</p>
          <div class="grid grid-cols-2 gap-4">
            {#each service.features as feature}
              <div class="flex items-center space-x-2">
                <div class="w-2 h-2 rounded-full" style="background-color: var(--color-primary)"></div>
                <span style="color: var(--color-dark)">{feature}</span>
              </div>
            {/each}
          </div>
          <div class="mt-8">
            <a href="/contact" class="btn btn-primary">Get Started</a>
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>