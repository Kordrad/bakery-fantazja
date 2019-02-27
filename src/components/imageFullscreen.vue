<template>
    <div class="fullscreen">
      <div class="container">
        <span class="close" @click="$emit('closeModal')"></span>
        <img :src="image" :alt="image.split('/')[2].split('.')[0]"/>
      </div>
    </div>
</template>

<script>
  export default {
    name: "imageFullscreen",
    props: {
      image: {
        default: 'https://freefrontend.com/assets/img/css-radio-buttons/radio-button-big-square-pure-css.png'
      }
    }
  }
</script>

<style lang="scss" scoped>
    .fullscreen {
      $small: 540px;
      $medium: 720px;
      $large: 960px;
      $extra: 1140px;


      position: fixed;
      z-index: 300;
      height: 100%;
      width: 100%;
      background-color: rgba(0, 0, 0, 0.75);
      top: 0;
      left: 0;
      .container {
        position: absolute;
        top: calc(50% + 5%);
        @media (min-width: $small) {
          top: 60%;
        }
        left: 50%;
        transform: translate(-50%, -50%);

        .close {
          right: 30px;
          top: 10px;
          position: absolute;
          &:after {
            content: '✖'; /* UTF-8 symbol */
            color: #2d2d2d;
            font: 20px/100% arial, sans-serif;
            position: absolute;
            text-decoration: none;
            text-shadow: 0 1px 0 #fff, 0 0 0 #fff;
            cursor: pointer;
          }
          &:hover{
            &:after{
              color: black;
            }
          }
        }
        img {
          max-width: 90vw;
          max-height: 70vH;
        }
      }
    }
</style>
