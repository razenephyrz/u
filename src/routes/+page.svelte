<style>
  .snap-y {
    scroll-snap-type: y mandatory;
  }

  .snap {
    scroll-snap-align: start;
  }
</style>

<script lang="ts">
  let audio: HTMLAudioElement | null = null;
  let isPlaying = false;
  let audioStarted = false;

  function toggleMusic() {
    if (!audio) {
      audio = new Audio('/alamak.mp3'); // path aman
      audio.loop = true;
      audio.volume = 0.4;
    }

    if (isPlaying) {
      audio.pause();
    } else {
      audio.play().catch(() => {});
    }

    isPlaying = !isPlaying;
  }

  function startMusicOnce() {
    if (!audioStarted) {
      toggleMusic();
      audioStarted = true;
    }
  }
</script>

<div
  class="h-screen overflow-y-scroll snap-y scroll-smooth"
  on:touchstart={startMusicOnce}
  on:click={startMusicOnce}
>

  <!-- PART 1 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="1.svg" class="max-w-full max-h-full" />
  </section>

  <!-- PART 2 (PNG LOCATION + MAP OVERLAY) -->
  <section class="snap h-screen relative flex items-center justify-center bg-black">

    <!-- PNG LOCATION -->
    <img src="part2 (1).png" class="max-w-full max-h-full" />

    <!-- MAP OVERLAY (MENIMPA PNG) -->
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

  <!-- PART 3 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="2.svg" class="max-w-full max-h-full" />
  </section>

  <!-- PART 4 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="3.svg" class="max-w-full max-h-full" />
  </section>

  <!-- PART 5 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="4.svg" class="max-w-full max-h-full" />
  </section>

</div>
