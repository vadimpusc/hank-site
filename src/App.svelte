<script>
  import Header from "./components/Header.svelte";
  import Hero from "./components/Hero.svelte";
  import About from "./components/About.svelte";
  import Filmography from "./components/Filmography.svelte";
  import Contact from "./components/Contact.svelte";
  import Footer from "./components/Footer.svelte";
</script>

<div class="page">
  <Header />

  <main>
    <section id="home">
      <Hero />
    </section>

    <section id="about">
      <About />
    </section>

    <section id="filmography">
      <Filmography />
    </section>

    <section id="contact">
      <Contact />
    </section>
  </main>

  <Footer />
</div>