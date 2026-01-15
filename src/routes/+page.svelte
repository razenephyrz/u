<style>
  .snap-y {
    scroll-snap-type: y mandatory;
  }

  .snap {
    scroll-snap-align: start;
  }
</style>

<script lang="ts">
  import { tick } from 'svelte';

  let audio: HTMLAudioElement | null = null;
  let audioStarted = false;
  let opened = false;

  async function openInvitation() {
    if (!audioStarted) {
      audio = new Audio('/alamak.mp3');
      audio.loop = true;
      audio.volume = 0.4;

      try {
        await audio.play();
        audioStarted = true;
      } catch {}
    }

    opened = true;

    // tunggu DOM update lalu scroll ke atas
    await tick();
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>

<!-- TAP AREA SAAT MASIH AMPL0P -->
{#if !opened}
  <button
    on:click={openInvitation}
    class="fixed inset-0 z-50 bg-transparent"
    aria-label="Open invitation"
  ></button>
{/if}

<div class="h-screen overflow-y-scroll snap-y scroll-smooth bg-black">

  {#if !opened}
    <!-- ================= AMPL0P (1.webp) ================= -->
    <section class="h-screen flex items-center justify-center snap">
      <img src="1.webp" class="max-w-full max-h-full" />
    </section>
  {:else}

    <!-- ================= 2.webp (jadi pertama) ================= -->
    <section class="h-screen flex items-center justify-center snap">
      <img src="2.webp" class="max-w-full max-h-full" />
    </section>

    <!-- ================= 3.webp + MAP ================= -->
    <section class="h-screen relative flex items-center justify-center snap">

      <img src="3.webp" class="max-w-full max-h-full" />

      <a
        href="https://maps.google.com/?q=Anthem+Jakarta"
        target="_blank"
        class="absolute
               top-[29%]
               left-1/2
               -translate-x-1/2
               w-[76%]
               h-[30%]
               z-10"
      >
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.395274125026!2d106.82089429999999!3d-6.2114852!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69f54c83d16e13%3A0x55e7d39fd5a16d37!2sAnthem%20Jakarta!5e0!3m2!1sid!2sid!4v1768405842801"
          class="w-full h-full border-0 pointer-events-none"
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </a>

    </section>

    <!-- ================= 4.webp ================= -->
    <section class="h-screen flex items-center justify-center snap">
      <img src="4.webp" class="max-w-full max-h-full" />
    </section>

    <!-- ================= 5.webp ================= -->
    <section class="h-screen flex items-center justify-center snap">
      <img src="5.webp" class="max-w-full max-h-full" />
    </section>

    <!-- ================= 6.webp ================= -->
    <section class="h-screen flex items-center justify-center snap">
      <img src="6.webp" class="max-w-full max-h-full" />
    </section>

  {/if}

</div>
