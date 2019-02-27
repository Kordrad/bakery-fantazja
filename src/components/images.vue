<template>
  <div class="grid">
    <img v-for="image in images" :src="image" :alt="image.split('/')[2].split('.')[0]" @click="handleModalOpen(image)"/>
    <image-fullscreen v-if="modalOpen" :image="modalImage" @closeModal="modalOpen = false"/>
  </div>
</template>

<script>
  import ImageFullscreen from './imageFullscreen.vue';
  export default {
    name: "images",
    components: { ImageFullscreen },
    data () {
      return {
        modalOpen: false,
        modalImage: null,
      }
    },
    methods: {
      handleModalOpen(image) {
        console.log(image);
        this.modalImage = image;
        return this.modalOpen = true;
      }
    },
    computed: {
      images () {
        const img = require.context('@/assets/img/gallery/', false, /[a-zA-Z0-9_-]+$/);
        return img .keys().map(x => img (x));
      },
    },
  }
</script>

<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;
  .grid {
    display: grid;
    grid-template-columns: 1fr ;
    grid-gap: 50px;
    @media (min-width: $small) {
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 1fr;
    }
    @media (min-width: $medium) {
      grid-template-columns: 1fr 1fr;
    }
    @media (min-width: $large) {
      grid-template-columns: 1fr 1fr 1fr 1fr;
    }

    img {
      cursor: pointer;
      object-fit: cover;
      width:100%;
      border-radius: 5px;
      border-width: 2px;
      border-style: inset;
      border-color: initial;
      border-image: initial;
      @media (min-width: $small) {
        height: 250px;
      }
      @media (min-width: $medium) {
        height: 300px;
      }
    }
  }
</style>
