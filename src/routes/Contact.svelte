<script lang="ts">
  let formData = {
    name: '',
    email: '',
    subject: '',
    message: ''
  };

  const handleSubmit = () => {
    console.log('Form submitted:', formData);
  };
</script>

<div class="pt-24 min-h-screen" style="background: linear-gradient(to bottom, var(--color-light), var(--color-dark))">
  <div class="container">
    <h1 class="section-title">Contact Us</h1>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 mb-20">
      <!-- Contact Form -->
      <div class="card p-8">
        <h2 class="text-2xl font-bold mb-6" style="color: var(--color-dark)">Get in Touch</h2>
        <form on:submit|preventDefault={handleSubmit} class="space-y-6">
          <div>
            <label for="name" class="block text-sm font-medium mb-1" style="color: var(--color-dark)">Name</label>
            <input
              type="text"
              id="name"
              bind:value={formData.name}
              class="w-full px-4 py-2 rounded-lg border"
              style="border-color: var(--color-dark); color: var(--color-dark)"
              required
            />
          </div>
          <div>
            <label for="email" class="block text-sm font-medium mb-1" style="color: var(--color-dark)">Email</label>
            <input
              type="email"
              id="email"
              bind:value={formData.email}
              class="w-full px-4 py-2 rounded-lg border"
              style="border-color: var(--color-dark); color: var(--color-dark)"
              required
            />
          </div>
          <div>
            <label for="subject" class="block text-sm font-medium mb-1" style="color: var(--color-dark)">Subject</label>
            <input
              type="text"
              id="subject"
              bind:value={formData.subject}
              class="w-full px-4 py-2 rounded-lg border"
              style="border-color: var(--color-dark); color: var(--color-dark)"
              required
            />
          </div>
          <div>
            <label for="message" class="block text-sm font-medium mb-1" style="color: var(--color-dark)">Message</label>
            <textarea
              id="message"
              bind:value={formData.message}
              rows="6"
              class="w-full px-4 py-2 rounded-lg border"
              style="border-color: var(--color-dark); color: var(--color-dark)"
              required
            ></textarea>
          </div>
          <button type="submit" class="btn btn-primary w-full">Send Message</button>
        </form>
      </div>

      <!-- Studio Info -->
      <div class="card p-8">
        <h2 class="text-2xl font-bold mb-6" style="color: var(--color-dark)">Studio Location</h2>
        <div class="aspect-w-16 aspect-h-9 mb-6 rounded-lg" style="background-color: var(--color-light)">
          <div class="w-full h-64 rounded-lg" style="background-color: var(--color-light)"></div>
        </div>
        <div class="space-y-4">
          <div>
            <h3 class="font-semibold" style="color: var(--color-dark)">Address</h3>
            <p style="color: var(--color-dark)">123 Music Avenue<br/>Los Angeles, CA 90028</p>
          </div>
          <div>
            <h3 class="font-semibold" style="color: var(--color-dark)">Contact</h3>
            <p style="color: var(--color-dark)">
              Email: contact@soundscapestudios.com<br/>
              Phone: (555) 123-4567
            </p>
          </div>
          <div>
            <h3 class="font-semibold" style="color: var(--color-dark)">Hours</h3>
            <p style="color: var(--color-dark)">
              Monday - Friday: 9:00 AM - 10:00 PM<br/>
              Saturday: 10:00 AM - 8:00 PM<br/>
              Sunday: By Appointment
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
