<template>
  <div>
    <v-flex goals-header relative>
      <v-avatar
              :size="56"
              color="grey lighten-4"
      >
        <v-badge right
               color="green">
          <template v-slot:badge>
            <span>315</span>
          </template>

          <img :src="require('../assets/avatar.png')"
               alt="avatar"
          >
        </v-badge>
      </v-avatar>

      <div class="goals-header__name">
        Дима Ефимов
      </div>
      <v-btn class="buy_ball" small absolute right>
        Купить баллы
      </v-btn>
    </v-flex>

    <v-card>
        <v-container
          fluid
          grid-list-lg
        >
          <v-layout row wrap>
            <v-flex xs12
                v-for="item in shops"
                :key="item.id"
            >
              <v-card :color="item.color" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">{{ item.title}}</div>
                        <div class="caption">{{ item.caption}}</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      :src="item.src"
                      height="125px"
                      cover
                    ></v-img>
                  </v-flex>
                </v-layout>
                <v-divider light></v-divider>
                <v-flex xs12 text-xs-center>
                 <v-btn>
                    <div class="mr-2">Потратить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading mr-2">{{ item.ball}}</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    data () {
      return {
        shops: null
      }
    },
    created() {
      this.getShops()
    },
    methods: {
      getShops() {
        axios.get('http://84.201.164.253/api/v1/shops', {})
                .then(response => {
                  this.shops = response.data.shops
                })
      }
    }
  }
</script>

<style>

</style>
