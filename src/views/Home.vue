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
    <section class="offer">
      <heading-color class="heading">
        <slot slot="title">Lorem ipsum</slot>
        <slot slot="paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Morbi odio neque, posuere nec placerat a, pretium ultricies velit.
        </slot>
      </heading-color>
      <div class="icons">
      <icons v-for="{ id, title, description, image, alt} in icons" :key="id"
             v-bind:title="title"
             v-bind:description="description"
             v-bind:alt="alt"
             v-bind:image="image"
      ></icons>
      </div>
    </section>
    <section class="map">
      <div style="overflow:hidden;width: 100%;height: 600px;">
        <iframe width="100%" height="700"
                src="https://maps.google.com/maps?width=100&amp;height=500&amp;hl=en&amp;q=Cukiernia%20Fantazja+(Cukiernia+Fantazja%C5%82)&amp;ie=UTF8&amp;t=&amp;z=15&amp;iwloc=B&amp;output=embed"
                frameborder="0" scrolling="no" marginheight="0" marginwidth="0">
        </iframe>
      </div>
      <br/>
    </section>
    <page-footer/>
  </div>
</template>
<script>
import Heading from '../components/heading.vue';
import HeadingColor from '../components/headingColor.vue';
import Icons from '../components/icons.vue';
import PageFooter from '../components/pageFooter';

export default {
  components: { PageFooter, Icons, HeadingColor, Heading },
  data() {
    return {
      icons: [
        {
          id: 1,
          image: require('../assets/img/icons/cake.svg'),
          alt: 'cake',
          title: 'Torty',
          description: 'To jest opis komponentu',
        },
        {
          id: 2,
          image: require('../assets/img/icons/dinner_food.svg'),
          alt: 'dinner_food',
          title: 'Placki',
        },
        {
          id: 3,
          image: require('../assets/img/icons/muffin.svg'),
          alt: 'muffin',
          title: 'Wypieki',
        },
      ],
    };
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
  /*SECTIONS*/
  .parallax {
    position: relative;
    min-height: 100vh;
    width: 100vw;
    background: url('../assets/img/home/cooking-1940689.jpg');
    background-position: center center;
    background-size: cover;
    .heading {
      position: absolute;
      top: 150px;
      height: calc(100% - 150px - 80px);
      left: 50%;
      transform: translateX(-50%);
    }

    .btn-primary {
      position: absolute;
      bottom: 25px;
      left: 50%;
      transform: translateX(-50%);
    }
  }
  .offer {
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

    .heading {
      display: block;
      position: relative;
      width: 50%;
      left: 50%;
      transform: translateX(-50%);
    }
    .icons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    .icons > *{
      width: 100%;
      padding: 30px;
    }
  }
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

  /* # SECTIONS # */


  @media only screen and (min-width: $small) {
    .parallax {
      min-height: 500px;
    }
    .offer {
      .icons {
        width: 90%;
        margin: 0 auto;
      }
      .icons > * {
        width: 50%;
      }
    }
    @media only screen and (min-width: $medium) {
      .parallax {
        min-height: 500px;
      }
      .offer {
        .icons {
          width: 75%;
        }
        .icons > * {
          width: 33.333%;
        }
      }
    }
  }
</style>
