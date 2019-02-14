<template>
    <footer>
      <img src="../assets/logo.png" class="logo"/>
      <div class="footerSections">
        <div class="media">
          <h3>Znajdź nas na</h3>
          <div>
            <a href="https://www.facebook.com/fantazjacukiernia/" target="_blank">
              <img src="../assets/img/footer/facebook.svg" alt="Facebook" class="icoMedia"/>
            </a>
            <a href="https://goo.gl/maps/TehyBwhQqgB2" target="_blank">
              <img src="../assets/img/footer/maps.png" alt="Google Maps" class="icoMedia"/>
            </a>
          </div>
        </div>
        <div class="workTime">
          <h3>Godziny Pracy</h3>
          <p>
            <span>Poniedziałek - Piątek</span>
            <span>10:00 - 18:00</span>
          </p>
          <p>
            <span>Sobota: 10:00 - 17:00</span>
            <span>Niedziela: 13:00 - 17:00</span>
            <br/>
            <span>Telefon</span>
            <a href="tel:+48503702543">+48 503 702 543</a>
          </p>
          </div>
        <div class="lookAt">
          <h3>Zajrzyj na</h3>
          <p>
            <a href="#/">Strona główna</a>
            <a href="#/about">Galeria</a>
            <a href="#/about">O nas</a>
            <a href="#/about">Kontakt</a>
            <a href="https://www.facebook.com/fantazjacukiernia/" target="_blank">Facebook</a>
            <a href="https://goo.gl/maps/TehyBwhQqgB2" target="_blank">Google Maps</a>
          </p>
        </div>
      </div>
      <div class="copyright">
        <span>© 2019 Design and made by Konrad Stępień</span>
      </div>
    </footer>
</template>

<script>
export default {
  name: 'pageFooter',
};
</script>


<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;
  footer {
    position: absolute;
    width: 100%;
    min-height: 150px;
    background-color: white;
    &:before {
      content: "";
      position: absolute;
      height: 80px;
      width: 100%;
      left: 0;
      white-space: pre;
      filter: drop-shadow(0px 15px 6px rgba(0, 0, 0, 0.3\5));
      background: url("../assets/wave.png") repeat-x left top;
      background-size: contain;
      z-index: 10;
      transform: rotate(180deg);
      top: -80px;
    }
    h3 {
      text-transform: uppercase;
    }
    .logo {
      position: absolute;
      left: 50%;
      transform: translate(-50%, -110px);
      z-index: 20;
    }

    .media {
      div{
        width: 30%;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        .icoMedia {
          height: 50px;
          width: 50px;
          border-radius: 50%;
        }
      }
    }
    .workTime, .media, .lookAt {
      text-align: center;
      margin-bottom: 50px;
    }
    .workTime, .lookAt {
      p{
        display: flex;
        flex-direction: column;
        span{
          width: 100%;
        }
      }
      span, a, h4 {
        color: #333;
        opacity: .75;
        text-decoration: none;
      }
    }
    .copyright {
      width: 80%;
      margin: 0 auto;
      text-align: center;
      margin-bottom: 25px;
      span {
        color: #333;
        opacity: 0.75;
      }
    }
  }

  @media only screen and (min-width: $small) {
    footer {
      position: relative;
      .footerSections{
        display: flex;
        flex-direction: row;
        width: 75%;
        margin: 0 auto;
        .workTime, .media, .lookAt {
          width: 33.333%;
        }
        .workTime {
          order: 1;
          text-align: left;
        }
        .media {
          order: 2;
          div {
            width: 60%;
          }
        }
        .lookAt {
          order: 3;
          text-align: right;
        }
      }
      .copyright {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        width: 33.33%;
        bottom: 0;
        span {
          opacity: 1;
        }
      }
    }
  }
  @media only screen and (min-width: $medium) {
    footer {
      .media {
        div {
          width: unset;
          max-width: 150px;
        }
      }
      .copyright {
        bottom: 40px;
      }
    }
  }
</style>
