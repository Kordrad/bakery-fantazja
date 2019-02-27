<template>
  <div class="contact">
    <section class="heading">
      <heading class="headingWhite">
        <slot slot="title">Lorem ipsum</slot>
        <slot slot="paragraph">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Morbi odio neque, posuere nec placerat a, pretium ultricies velit.
        </slot>
      </heading>
    </section>
    <cloud-section>
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
        <div class="form">
          <heading-color class="headingColor">
            <slot slot="title">Napisz Do Nas</slot>
          </heading-color>
          <contact-form/>
        </div>
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
      .form {
        width: $widElements;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
      }
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
      .mapDiv {
        height: 500px !important;
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
    .flex {
      flex-direction: row !important;
      .mapDiv {
        width: 50% !important;
        height: auto !important;
        transform: unset;
      }
      .form {
        padding: 0 20px;
        width: 50% !important;
        position: unset !important;
        right: 0;
        transform: unset !important;

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
      padding-top: 90px;

      .headingColor {
        position: absolute;
        left: 50%;
        transform: translate(-50%, -100px);

      }
    }
  }
</style>
