<template>
  <div class="home">
    <section class="parallax">
      dsa
    </section>
  </div>
</template>
<script>
  import Heading from '../components/heading';

  export default {
    components: { Heading }
  };
</script>
<style lang="scss" scoped>
  .home {
    position: absolute;
    left: 0;
  }

  .parallax {
    position: relative;
    height: 100vh;
    width: 100vw;
    background: url('../assets/img/home/cooking-1940689.jpg');
    background-position: center center;
    background-size: cover;
  }

  .heading {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>
