<template>
  <div class="gallery">
    <section class="heading">
      <heading class="headingWhite">
        <slot slot="title">Nasza galeria wypieków</slot>
        <slot slot="paragraph">
          Przedstawiamy wam kilka naszych wypieków. <br/>
          Ale niech państwo pamiętają, że to jedynie kilka z nich.<br/>
          Zapraszamy na naszego facebook'a , aby zobaczyć więcej! <a style="color: white" href="https://www.facebook.com/fantazjacukiernia/" target="_blank">@FantazjaCukiernia</a>
        </slot>
      </heading>
    </section>
    <cloud-section>
      <images class="images"/>
    </cloud-section>
    <map-section/>
    <page-footer/>
  </div>
</template>
<script>
import PageFooter from '../components/pageFooter.vue';
import Heading from '../components/heading.vue';
import CloudSection from '../components/cloudSection.vue';
import MapSection from '../components/mapSection.vue';
import Images from '../components/images.vue';

export default {
  components: {
    Images,
    MapSection,
    CloudSection,
    Heading,
    PageFooter,
  },
};
</script>
<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;
  .gallery {
    .heading {
      position: relative;
      min-height: 500px;

      &:before {
        content: '';
        white-space: pre;
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 100%;
        background: url('../assets/img/aboutus/bakery-1868925.jpg') center center;
        filter: blur(5px) contrast(1.25) brightness(.5) hue-rotate(325deg);
        background-size: cover;
      }

      .headingWhite {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
      }
    }
    .images {
      width: 90%;
      margin: 0 auto;
    }
  }
</style>
