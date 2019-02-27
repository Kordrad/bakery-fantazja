<template>
  <div class="about">
    <section class="heading">
      <heading class="headingWhite">
        <slot slot="title">Lorem ipsum</slot>
        <slot slot="paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Morbi odio neque, posuere nec placerat a, pretium ultricies velit.
        </slot>
      </heading>
    </section>
    <cloud-section class="aboutUs">
      <div class="flex">
        <heading-color class="headingColor">
          <slot slot="title">Cukiernia fantazja</slot>
          <slot slot="paragraph">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. At beatae expedita facilis nesciunt optio quam
                veniam voluptatibus. Aliquam, amet debitis earum id labore magnam nostrum quasi sed tempora totam. Officia?
                Ad adipisci alias atque esse est facilis maxime molestiae quam ratione saepe. Dolore doloribus eos esse
                eum facere harum hic iure maiores non optio quasi quisquam quo totam, veniam voluptatum!
                Aliquam architecto asperiores doloribus eum excepturi expedita ipsum itaque molestias officiis recusandae
                reiciendis, suscipit ullam veniam? Ab autem delectus, earum explicabo ipsa laboriosam, magnam minima minus
                quae recusandae unde voluptatum!
                Aperiam, architecto, commodi cupiditate dicta expedita incidunt mollitia non possimus quas quibusdam
                repellendus sit ut veniam! Aliquid ducimus fuga illum, impedit itaque labore mollitia nihil nobis numquam
                obcaecati reiciendis vero!
                Ea eum fugiat ipsam iusto magni minus necessitatibus perferendis porro possimus quaerat quis recusandae
                reiciendis reprehenderit sit temporibus ullam, unde voluptas. Laudantium, repudiandae, voluptatibus. Ab
                dolores libero quaerat quam veritatis.
                Culpa, delectus dignissimos et fugiat illo iure perferendis! Ab, adipisci aliquam animi at cum eum fugiat
                minus molestias nisi odio possimus quaerat quasi quis reiciendis repellat reprehenderit sit tenetur unde.
          </slot>
        </heading-color>
        <div class="chef">
          <img src="../assets/img/aboutus/chef-17736722.png" alt="Chef">
        </div>
      </div>
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
import HeadingColor from '../components/headingColor.vue';

export default {
  components: {
    HeadingColor, MapSection, CloudSection, Heading, PageFooter,
  },
};
</script>
<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;
  .about {
    .heading {
      position: relative;
      min-height: 500px;
      &:before{
        content: '';
        white-space: pre;
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 100%;
        background: url('../assets/img/aboutus/bakery-1868925.jpg') center center;
        filter: blur(5px) contrast(1.25) brightness(.5);
        background-size: cover;
      }
      .headingWhite {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
      }
    }
    .aboutUs {
      min-height: 200px;
      padding: 40px;
      .chef {
        width: 100%;
        padding: 15px;
        img {
          width: 100%;
        }
      }
    }
  }
  @media only screen and (min-width: $small) {
    .about {
      .aboutUs{
        .flex{
          position: relative;
          display: flex;
          $size: 30%;
          .chef {
            order: 1;
            padding: 0;
            width: $size;
            position: relative;
            img {
              position: absolute;
              left:50%;
              top: 50%;
              transform:translate(-50%, -50%);
            }

          }
          .headingColor {
            order: 2;
            width: 100% - $size;
            padding: 10px;
          }
        }
      }
    }
  }
  @media only screen and (min-width: $medium) {
    .about {
      .headingColor {
        padding-left: 50px !important;
      }
      .chef {
        img {
          width: 100%;
          max-width: 300px;
        }
      }
    }
  }
</style>
