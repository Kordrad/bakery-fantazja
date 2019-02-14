<template>
  <form>
    <label>
      <input type="text" name="pame" placeholder="Imię">
    </label>
    <label>
      <input type="text" name="phone" placeholder="Telefon">
    </label>
    <label>
      <textarea placeholder="Napisz coś do nas!">Dzień dobry! Zainteresowała mnie pani cukiernia i...</textarea>
    </label>
    <input type="submit" class="btn-primary">
  </form>
</template>

<script>
export default {
  name: 'contactForm',
};
</script>

<style lang="scss" scoped>
  $small: 540px;
  $medium: 720px;
  $large: 960px;
  $extra: 1140px;
  form {
    display: flex;
    flex-direction: column;
    margin-bottom: 50px;
    label {
      input {
        height: 30px;
      }
      textarea {
        min-height: 100px;
        resize: vertical;
      }
      input, textarea {
        padding: 3%;
        font-family: "Varela Round", serif;
        width: 100%;
        margin-bottom: 20px;
        border-radius: 5px;
        border-width: 2px;
        border-style: inset;
        border-color: initial;
        border-image: initial;
        background-color: #eee;
      }
    }

    .btn {
      font-family: "Varela Round", serif;
      padding: 10px 20px;
      text-transform: uppercase;
      background: linear-gradient(to right, #d41f23 0%,#e96b5b 100%);
      border: 1px solid papayawhip;
      color: white;
      border-radius: 15px;
      outline: none;
      &:hover{
        filter: brightness(90%);
      }

    }
  }

  @media only screen and (min-width: $large) {
    label input {
      height: 40px !important;
    }
    textarea {
      min-height: 200px !important;
    }
  }
</style>
