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
    <cloud-section class="offer">
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
    </cloud-section>
    <map-section/>
    <page-footer/>
  </div>
</template>
<script>
import Heading from '../components/heading.vue';
import HeadingColor from '../components/headingColor.vue';
import Icons from '../components/icons.vue';
import PageFooter from '../components/pageFooter.vue';
import MapSection from '../components/mapSection.vue';
import CloudSection from '../components/cloudSection';

export default {
  components: {
    CloudSection,
    MapSection, PageFooter, Icons, HeadingColor, Heading,
  },
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
    background: url('../assets/img/home/cooking-1940689.jpg') center center;
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
