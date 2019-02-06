<template>
  <div class="home">
    <section class="parallax">
      <heading class="heading">
        <slot slot="title">Cukiernia Fantazja</slot>
        <slot slot="paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Morbi odio neque, posuere nec placerat a, pretium ultricies velit.
        </slot>
        <router-link to="/about">
          <button class="btn-primary">Skontaktuj się z nami</button>
        </router-link>
      </heading>
    </section>
  </div>
</template>
<script>
import Heading from '../components/heading.vue';


export default {
  components: { Heading },
  data() {
    return {
      scrolled: false,
    };
  },
  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 0;
    },
  },
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll);
  },
};

</script>
<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;

  .home {
    position: absolute;
    left: 0;
  }

  .parallax {
    position: relative;
    min-height: 100vh;
    width: 100vw;
    background: url('../assets/img/home/cooking-1940689.jpg');
    background-position: center center;
    background-size: cover;
  }

  .heading {
    position: absolute;
    top: 150px;
    height: calc(100% - 150px - 70px);
    left: 50%;
    transform: translateX(-50%);
  }

  .btn-primary {
    position: absolute;
    bottom: 25px;
    left: 50%;
    transform: translateX(-50%);
  }


  @media only screen and (min-width: $medium) {
    .parallax {
      min-height: 500px;
    }
  }
</style>
