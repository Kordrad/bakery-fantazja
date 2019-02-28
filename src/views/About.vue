<template>
  <div class="about">
    <section class="heading">
      <heading class="headingWhite">
        <slot slot="title">Cukiernia Fantazja</slot>
        <slot slot="paragraph">
          Tak! To właśnie jedno załogowa firma! <br/>
          Wraz z pasją i pełną energi to tworzenia tego czego się kocha!
        </slot>
      </heading>
    </section>
    <cloud-section class="aboutUs">
      <div class="flex">
        <heading-color class="headingColor">
          <slot slot="title">O nas słów kilka...</slot>
          <slot slot="paragraph">
            `(...) Specjalnością właścicielki są torty. Pani piecze sama, to domowe wypieki, sama robi masy, biszkopty.
            Stara się, by było ‘tak jak dawniej’. Pomysł na założenie Fantazji wziął się stąd, że właścicielka długo
            zajmowała się wychowywaniem dzieci, a kiedy te dorosły, postanowiła wziąć sprawy w swoje ręce. Wszystkim,
            którzy próbowali jej wypieków, bardzo smakowało, więc otworzyła swoją cukiernię. Teraz klienci wybierają
            właśnie Fantazję ze względu na sentyment do smaku domowych wypieków. Ważne jest indywidualne podejście do
            każdego klienta. <br/>Jak mówi właścicielka, nie ważna jest ilość zamówień, a zadowolenie kupującego.`
            <br>
            <a style="color: #888888" href="https://nowiny24.pl/mistrzowie-smaku-zobacz-liderow-powiatowych-kategorii-plebiscytu/ga/13347949/zd/30394530" target="_blank">~Nowiny24.pl</a>

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
      HeadingColor,
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
  .about {
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
      .aboutUs {
        .flex {
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
              left: 50%;
              top: 50%;
              transform: translate(-50%, -50%);
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
