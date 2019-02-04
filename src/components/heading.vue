<template>
  <div>
    <h1>Cukiernia Fantazja</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      Morbi odio neque, posuere nec placerat a, pretium ultricies velit.
    </p>
  </div>
</template>

<script>
  export default {
    name: 'heading',
  };
</script>

<style lang="scss" scoped>
  h1{
    border: 1px solid red;
    position: relative;
    &:before, &:after{
      $height: 25px;
      content: "";
      position: absolute;
      white-space: pre;
      background-color: white;
      mask-image: url(../assets/img/heading/leaf.svg);
      height: $height;
      width: $height*2;
      border: 1px solid aqua;
      background-size: contain;
      background-repeat: no-repeat;
      display: block;
      fill: white;
    }
    &:before {
      left: -50%;
      /*transform: translate(50%);*/
      transform: scaleX(-1);
    }
  }
  p {
    font-style: italic;
  }
  h1 ,p {
    text-align: center;
    color: white;
    text-shadow: 0 0 5px rgba(0, 0, 0, 0.7);
  }
</style>
