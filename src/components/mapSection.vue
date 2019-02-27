<template>
  <section class="map">
    <div style="overflow:hidden;width: 100%;height: 600px; position: relative">
      <iframe width="100%" height="650" style="position: absolute; top: -100px;"
              :src="link"
              frameborder="0" scrolling="no" marginheight="0" marginwidth="0" allowfullscreen>
      </iframe>
    </div>
  </section>
</template>

<script>
export default {
  name: 'mapSection',
  props: {
    link: {
      type: String,
      default: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2000!2d22.318837697102833!3d50.24851069030172!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x473cc3a1cc3b92a1%3A0xb2f90e855f02f21e!2sCukiernia+Fantazja!5e0!3m2!1spl!2spl!4v1549908118283',
    },
  },
};
</script>

<style scoped>
  .map {
    position: relative;
    height: 500px;
    #gmap_canvas img {
      max-width: none !important;
      background: none !important
    }
    div {
      position: absolute;
      top: -100px;
    }
  }
</style>
