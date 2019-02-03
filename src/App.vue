<template>
  <div class="app">
    <nav>
      <router-link to="/">
        <img class="logo" src="./assets/logo.png" alt="home"/>
      </router-link>

      <input type="checkbox" name="navToggle"/>
      <span class="burger-squeeze"></span>
      <div class="menu">
        <router-link to="/">Strona Główna</router-link>
        <router-link to="/about">Galeria</router-link>
        <router-link to="/about">O nas</router-link>
        <router-link to="/about">Kontakt</router-link>
      </div>
    </nav>
    <router-view/>
  </div>
</template>
<script>

</script>
<style lang="scss">
  @import "style";

  $burger-height: 3px;
  $burger-gap: 4px + $burger-height;
  .burger-squeeze {
    transition: background-color .01s .5s;

    &, &:before, &:after {
      background-color: #555;
      z-index: 98;
      height: $burger-height;
      width: 25px;
      position: absolute;
    }

    &:before, &:after {
      content: "";
      white-space: pre;
      transition: transform .5s, bottom .5s .5s;
    }

    &:before {
      bottom: $burger-gap;
    }

    &:after {
      bottom: -$burger-gap;
    }

    transform: translateY(20px);
  }

  img.logo {
    height: 100px;
    width: 100px;
    filter: drop-shadow(0px 0px 6px rgba(0, 0, 0, 0.35));
  }

  nav {
    font-family: 'Varela Round', sans-serif;
    position: fixed;
    left: 0;
    top: 0;
    height: 50px;
    width: 100%;

    &:after {
      content: "";
      position: absolute;
      height: 80px;
      width: 100%;
      left: 0;
      white-space: pre;
      filter: drop-shadow(0px 15px 6px rgba(0, 0, 0, 0.35));
      background: url("./assets/wave.png") repeat-x left top;
      background-size: contain;
      z-index: -1;
    }


    $checkbox-size: 30px;
    $checkbox-right: 20px;
    $checkbox-top: 5px;

    input[name="navToggle"], .burger-squeeze {
      position: absolute;
      right: $checkbox-right;
      top: $checkbox-top;
      z-index: 999;
    }

    input[name="navToggle"] {
      height: $checkbox-size;
      width: $checkbox-size;
      opacity: 0;
      z-index: 9999;
    }

    img.logo {
      position: absolute;
      left: 50%;
      top: 10px;
      transform: translateX(-50%);
      /*z-index: 100;*/
    }

    .menu {
      position: fixed;
      height: 100vh;
      width: 90vw;
      max-width: 500px;
      right: -100%;
      top: 0;
      background-color: white;
      display: flex;
      flex-direction: column;
      transition: 1s;
      transition-timing-function: cubic-bezier(.35, .7, .65, .99);
      box-shadow: 15px 0 15px 15px rgba(0, 0, 0, 0.5);
      text-transform: uppercase;


      & > * {
        &:first-child {
          margin-top: 100px;
        }

        text-decoration: none;
        color: #555;
        text-align: right;
        font-size: 1.5rem;
        padding: 1.2rem 3rem;
      }
    }

    input[name="navToggle"]:checked ~ .burger-squeeze {
      background-color: rgba(0, 0, 0, 0);

      &:after, &:before {
        bottom: 0;
        transition: bottom .5s, transform .5s .5s;
      }

      &:after {
        transform: rotate(45deg);
      }

      &:before {
        transform: rotate(-45deg);
      }
    }

    input[name="navToggle"]:checked ~ .menu {
      right: 0;
    }

  }

  /*RESPONSIVE*/
  @media only screen and (min-width: $small) {
    nav {
      input[name="navToggle"], .burger-squeeze {
        display: none;
      }

      .menu {
        position: absolute;
        height: auto;
        width: 95%;
        left: 50%;
        top: 20px;
        transform: translateX(-50%);
        max-width: unset;
        display: inline-grid;
        grid-template-columns: repeat(2, 1fr) 0px repeat(2, 1fr);
        /*grid-auto-rows: minmax(100px, auto);*/
        grid-template-areas: "link-1 link-2 . link-3 link-4 ";
        background-color: unset;
        box-shadow: unset;

        & > * {
          &:first-child {
            margin-top: unset;
          }

          @for $i from 1 through 4 {
            &:nth-child(#{$i}) {
              grid-area: link-#{$i};
            }
          }
          padding: 0;
          text-align: center;
          font-size: .9rem;
        }


      }

      img.logo {
        height: 125px;
        width: 125px;
        top: 25px;
      }
    }
  }

  @media only screen and (min-width: $medium) {
    nav {
      .menu {
        grid-template-columns: repeat(2, 1fr) 30px repeat(2, 1fr);
        width: 80%;
      }
    }
  }

  @media only screen and (min-width: $large) {
    nav {
      .menu {
        grid-template-columns: repeat(2, 1fr) 50px repeat(2, 1fr);
        width: 70%;
      }
    }
  }

  @media only screen and (min-width: $extra) {
    nav {
      .menu {
        width: 50%;
      }
    }
  }
</style>
