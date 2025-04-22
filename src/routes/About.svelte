<script lang="ts">
  const team = [
    {
      name: 'Logan Lanning',
      role: 'Producer, Songwriter',
      image: '/vite.svg',
      bio: 'Producer and writer extraordinaire.'
    },
    {
      name: 'Gino Quartucci',
      role: 'Producer, Songwriter',
      image: '/vite.svg',
      bio: 'Sound design wizard.'
    },
    {
      name: 'Devin Hill',
      role: 'Engineer, Songwriter',
      image: '/vite.svg',
      bio: 'Tech bro.'
    }
  ];
</script>

<div class="pt-24 min-h-screen" style="background: linear-gradient(to bottom, var(--color-light), var(--color-dark))">
  <div class="container">
    <h1 class="section-title">About Us</h1>

    <div class="card p-8 mb-16">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-2xl font-bold mb-6" style="color: var(--color-dark)">Our Story</h2>
        <p class="mb-6" style="color: var(--color-dark)">
          Founded in 2020, Lions Mind Entertainment has quickly become one of the most sought-after music production facilities in Los Angeles. Our state-of-the-art studio combines cutting-edge technology with creative expertise to help artists achieve their vision.
        </p>
        <p style="color: var(--color-dark)">
          We believe in the power of collaboration and innovation, working closely with artists to develop their unique sound while maintaining the highest standards of production quality.
        </p>
      </div>
    </div>

    <h2 class="text-2xl font-bold text-center mb-12" style="color: var(--color-dark)">Meet Our Team</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
      {#each team as member}
        <div class="card group p-6 text-center">
          <div class="w-32 h-32 rounded-full overflow-hidden mx-auto mb-6 ring-4 transition-all"
               style="ring-color: var(--color-primary)">
            <img src={member.image} alt={member.name} class="w-full h-full object-cover" />
          </div>
          <h3 class="text-xl font-semibold mb-2 transition-colors group-hover:text-[var(--color-primary)]">{member.name}</h3>
          <p class="mb-4" style="color: var(--color-primary)">{member.role}</p>
          <p style="color: var(--color-dark)">{member.bio}</p>
        </div>
      {/each}
    </div>

    <div class="card p-8 text-white text-center" style="background: linear-gradient(to right, var(--color-primary), var(--color-secondary))">
      <h2 class="text-2xl font-bold mb-6">Ready to Create Something Amazing?</h2>
      <p class="mb-8">Let's work together to bring your musical vision to life.</p>
      <a href="/contact" class="btn" style="background: white; color: var(--color-primary);">Get in Touch</a>
    </div>
  </div>
</div>
