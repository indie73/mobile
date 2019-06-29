<template>
  <div class="login">
    <h1>Вход</h1>
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
                type="tel"
                placeholder="****"
                hide-details
                value=""
                required
        ></v-text-field>
      </div>
      <div class="login__submit">
        <v-btn v-on:click="sendSMS()" v-if="!sendedSMS">Отправить</v-btn>
        <router-link :to="'home'" v-if="sendedSMS" class="v-btn theme--light">
          Подтвердить
        </router-link>
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

  .login .v-form {
    text-align: center;
  }

  .login__logo {

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
</style>
