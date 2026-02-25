<script>
  import { onMount } from "svelte";
  import Filmography from "./components/Filmography.svelte";

  function sendHeight() {
    // Make sure we grab the full document height, not just body
    const height = Math.max(
      document.body.scrollHeight,
      document.documentElement.scrollHeight
    );

    window.parent.postMessage({ type: "resize-iframe", height }, "*");
  }

  onMount(() => {
    // Initial
    sendHeight();

    // Update when layout/content changes (images load, fonts load, etc.)
    const ro = new ResizeObserver(() => sendHeight());
    ro.observe(document.documentElement);

    // Extra safety for mobile/font/image timing
    window.addEventListener("load", sendHeight);
    window.addEventListener("resize", sendHeight);

    // If your filmography loads images, this helps a lot
    const imgTimer = setInterval(sendHeight, 300);
    setTimeout(() => clearInterval(imgTimer), 4000);
  });
</script>

<div class="page">
  <main>
    <section id="filmography">
      <Filmography />
    </section>
  </main>
</div>