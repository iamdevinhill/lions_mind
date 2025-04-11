<script lang="ts">
  import { Router, Link, Route } from "svelte-routing";
  import Header from "./lib/components/Header.svelte";
  import Footer from "./lib/components/Footer.svelte";
  import Home from "./routes/Home.svelte";
  import Services from "./routes/Services.svelte";
  import Portfolio from "./routes/Portfolio.svelte";
  import About from "./routes/About.svelte";
  import Contact from "./routes/Contact.svelte";

  export let url = "";
</script>

<Router {url}>
  <div class="flex flex-col min-h-screen">
    <Header />
    <main class="flex-grow">
      <Route path="/" component={Home} />
      <Route path="/services" component={Services} />
      <Route path="/portfolio" component={Portfolio} />
      <Route path="/about" component={About} />
      <Route path="/contact" component={Contact} />
    </main>
    <Footer />
  </div>
</Router>