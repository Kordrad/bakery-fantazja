<template>
  <div class="contact">
    <section class="heading">
      <heading class="headingWhite">
        <slot slot="title">Napisz do Nas!</slot>
        <slot slot="paragraph">
          Jeśli jesteś zainteresowany naszymi wypiekami,<br/>
          bądź chciał(a) byś dowiedzieś się czegoś to się nie krępój!<br/>
          Napisz do nas poprzez formularz, facebook, bądż zadzwoń do nas!
        </slot>
      </heading>
    </section>
    <cloud-section>
      <heading-color class="headingColor">
        <slot slot="title">Skontaktuj się z nami!</slot>
      </heading-color>
      <div class="flex">
        <div class="mapDiv">
          <iframe width="100%" height="100%"
                  style="
                          border-radius: 5px;
                          border-width: 2px;
                          border-style: inset;
                          border-color: initial;
                          border-image: initial;"
                  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2000!2d22.318837697102833!3d50.24851069030172!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x473cc3a1cc3b92a1%3A0xb2f90e855f02f21e!2sCukiernia+Fantazja!5e0!3m2!1spl!2spl!4v1549908118283"
                  frameborder="0" scrolling="no" marginheight="0" marginwidth="0" allowfullscreen>
          </iframe>
        </div>
        <div class="icons">
          <a class="fab fa-facebook-f" target="_blank" href="https://www.facebook.com/fantazjacukiernia/"></a>
          <a class="fab fa-facebook-messenger" target="_blank" href="https://m.me/fantazjacukiernia"></a>
          <a class="far fa-envelope" href="mailto:fantazjakontakt@gmail.com"></a>
          <a class="fas fa-phone" href="tel:+48535702546"></a>
          <a href="https://goo.gl/maps/TehyBwhQqgB2" target="_blank">
            <img src="../assets/img/footer/maps.png" alt="Google Maps" class="icoMedia fas"/>
          </a>
        </div>
        <!--<div class="form">
          &lt;!&ndash;<heading-color class="headingColor">
            <slot slot="title">Napisz Do Nas</slot>
          </heading-color>&ndash;&gt;
          &lt;!&ndash;<contact-form/>&ndash;&gt;
        </div>-->
      </div>
    </cloud-section>
    <section class="address">
      <div class="details">
        <heading class="headingWhite">
          <slot slot="title">Szczegółowe Informacje</slot>
        </heading>
        <div class="moreDetails">
          <div class="contactDetails">
            <h2>Kontakt</h2>
            <a href="mailto:FantazjaKontakt@gmail.com">FantazjaKontakt@gmail.com</a>
            <a href="tel:+48503702543">503 702 543</a>
          </div>
          <div class="addressDetails">
            <h2>Adres</h2>
            <span>Brzóza Królewska 867,</span>
            <span>37-307 Brzóza Królewska</span>
          </div>
        </div>
      </div>
    </section>
    <page-footer/>
  </div>
</template>
<script>
import Heading from '../components/heading.vue';
import CloudSection from '../components/cloudSection.vue';
import PageFooter from '../components/pageFooter.vue';
import ContactForm from '../components/contactForm.vue';
import HeadingColor from '../components/headingColor.vue';

export default {
  components: {
    HeadingColor,
    ContactForm,
    PageFooter,
    CloudSection,
    Heading,
  },
};
</script>
<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;

  $fab-size: 60px;
  $fap-padi: 15px;
  .fab , .fas, .far{
    text-align: center;
    padding: $fap-padi;
    margin: 10px;
    font-size: $fab-size - $fap-padi *2;
    height: $fab-size;
    width: $fab-size;
    text-decoration: none;
    border-radius: 50%;
    color: white;
    &.fa-facebook-f {background: #3B5998;}
    &.fa-phone {background: #089800;}
    &.fa-envelope {background: #d44638;}
    &.fa-facebook-messenger {background: #0085FF;}
    &.icoMedia{ padding: 0;}
  }

  .contact {
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
    .flex {
      $widElements: 90%;
      display: flex;
      flex-direction: column;
      position: relative;
      .mapDiv {
        width: 100%;
        overflow:hidden;
        height: 400px;
        position: relative;
        margin-bottom: 50px;
        & > *{
          position: absolute;
          width: $widElements;
          left: 50%;
          transform: translateX(-50%);
          filter: hue-rotate(-40deg);
        }
      }
      .icons {
        flex-wrap: wrap;
        text-align: center;
        width: 90%;
        margin: 0 auto;
        display: flex;
        justify-content: space-around;

      }
      /*.form {
        width: $widElements;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
      }*/
    }
  }

  .address {
    padding: 100px 0;
    min-height: 600px;
    background-color: #282c2f;
    color: white;
    position: relative;
    .details {
      position: absolute;
      left: 50%;
      top:50% ;
      transform: translate(-50%, -50%);
      .headingWhite {
        width: 80%;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
      }
      .moreDetails {
        text-align: center;
        a {
          color: white;
          text-decoration: none;
        }
        .contactDetails, .addressDetails {
          display: flex;
          flex-direction: column;
        }
      }
    }
  }
  @media only screen and (min-width: $small) {
    .flex {
      flex-direction: column-reverse !important;
      .mapDiv {
        height: 500px !important;
      }
      .icons {

      }
    }
    .address {
      min-height: 500px;
      .details {
        width: 80%;
        .moreDetails {
          display: flex;
          justify-content: space-between;
          .contactDetails, .addressDetails {
            width: 50%;
          }
          .contactDetails {
            text-align: left;
          }
          .addressDetails {
            text-align: right;
          }
        }
      }
    }
  }
  @media only screen and (min-width: $medium) {
    &.fa-phone {display: none}
    &.fa-envelope {display: none}
    .flex {
      /*flex-direction: row !important;*/
      .mapDiv {
        height: 400px !important;
        transform: unset;
      }
      /*.form {
        padding: 0 20px;
        width: 50% !important;
        position: unset !important;
        right: 0;
        transform: unset !important;

      }*/
      .icons {
        width: 50% !important;
        padding-bottom: 50px;
      }
    }
    .address {
      .details {
        width: 60%;
      }
    }
  }
  @media only screen and (min-width: $large) {
    .flex {
      width: 85% !important;
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      /*padding-top: 90px;*/

      .headingColor {
        position: absolute;
        left: 50%;
        transform: translate(-50%, -100px);

      }
    }
  }
</style>
