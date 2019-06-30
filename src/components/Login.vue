<template>
  <div class="login">
    <h1>
      <img
              :src="require('../assets/logo.png')"
              alt="">
      Вход
    </h1>
    <v-form>
      <div class="login__phone" v-if="!sendedSMS">
        <div class="login__phone__label">Ваш номер телефона:</div>
        <v-text-field
                prefix="+7"
                mask="phone"
                type="tel"
                hide-details
                required
        ></v-text-field>
        <div class="login__phone__text">
          На ваш номер прийдет SMS-код
        </div>
      </div>
      <div class="login__phone" v-if="sendedSMS">
        <div class="login__phone__label">Код:</div>
        <v-text-field
                type="password"
                placeholder="****"
                hide-details
                value=""
                maxlength="4"
                required
        ></v-text-field>
      </div>
      <div class="login__submit">
        <v-btn v-on:click="sendSMS()" v-if="!sendedSMS">Отправить</v-btn>
        <router-link :to="'home'" v-if="sendedSMS" class="v-btn theme--light">
          Подтвердить
        </router-link>
      </div>
      <div class="login__social">
        <div class="login__social__title">
          Войти с помощью соцсетей
        </div>
        <ul class="login__social__list">
          <li>
            <router-link :to="'home'">
              <img
                      :src="require('../assets/mail.svg')"
                      alt="">
            </router-link>
          </li>
          <li>
            <router-link :to="'home'">
              <img
                      :src="require('../assets/facebook.svg')"
                      alt="">
            </router-link>
          </li>
          <li>
            <router-link :to="'home'">
              <img
                      :src="require('../assets/vk.svg')"
                      alt="">
            </router-link>
          </li>
          <li>
            <router-link :to="'home'">
              <img
                      :src="require('../assets/ok.svg')"
                      alt="">
            </router-link>
          </li>
        </ul>
      </div>
    </v-form>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        sendedSMS : false,
      }
    },
    methods: {
      sendSMS() {
        this.sendedSMS = true;
      },
    }
  }
</script>

<style>
  .login {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }

  .login h1 {
    margin-bottom: 30px;
  }

  .login h1 img {
    display: inline-block;
    vertical-align: middle;
    margin-top: -2px;
    margin-right: 10px;
    width: 40px;
  }

  .login .v-form {
    text-align: center;
  }

  .login__logo {
    margin-bottom: 15px;
  }

  .login__phone {
    margin-bottom: 10px;
  }

  .login__phone__label {
  }

  .login__phone__text {
    margin-top: 2px;
    font-size: 12px;
    color: rgba(0,0,0,0.54);
  }

  .login__phone .primary--text {
    color: #000 !important;
  }

  .login__submit{
    text-align: center;
  }

  .login__social {
    margin-top: 35px;
  }

  .login__social__title {
    margin-bottom: 10px;
  }

  .login__social__list {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  .login__social__list li {
    display: inline-block;
    vertical-align: middle;
    margin: 0 10px;
  }

  .login__social__list li img {
    width: 32px;
  }
</style>
