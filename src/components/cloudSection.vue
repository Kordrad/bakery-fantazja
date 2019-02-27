<template>
  <section class="cloud">
    <slot></slot>
  </section>
</template>

<script>
export default {
  name: 'cloudSection',
};
</script>

<style lang="scss" scoped>
  section {
    z-index: 5;
    background-color: white;
    position: relative;
    &:before ,&:after{
      content: "";
      position: absolute;
      height: 80px;
      width: 100%;
      left: 0;
      white-space: pre;
      filter: drop-shadow(0px 15px 6px rgba(0, 0, 0, 0.3\5));
      background: url("../assets/wave.png") repeat-x left top;
      background-size: contain;
      z-index: -1;
    }
    &:before {
      transform: rotate(180deg);
      top: -80px;
    }
    &:after {
      bottom: -80px;
    }
    min-height: 200px;
  }
</style>
