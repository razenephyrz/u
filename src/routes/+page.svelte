<style>
  .snap-y {
    scroll-snap-type: y mandatory;
  }

  .snap {
    scroll-snap-align: start;
  }
</style>

<div class="h-screen overflow-y-scroll snap-y scroll-smooth">

  <!-- PART 1 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="1.svg" class="max-w-full max-h-full" />
  </section>

  <!-- PART 2 (SVG + MAPS OVERLAY) -->
  <section class="snap h-screen relative flex items-center justify-center bg-black">

    <!-- SVG -->
    <img src="2.svg" class="max-w-full max-h-full" />

    <!-- MAP OVERLAY -->
    <a
      href="https://maps.google.com/?q=Anthem+Jakarta"
      target="_blank"
      class="absolute
             top-[58%]
             left-1/2
             -translate-x-1/2
             w-[75%]
             h-[26%]
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
    <img src="3.svg" class="max-w-full max-h-full" />
  </section>

  <!-- PART 4 -->
  <section class="snap h-screen flex items-center justify-center bg-black">
    <img src="4.svg" class="max-w-full max-h-full" />
  </section>

</div>
