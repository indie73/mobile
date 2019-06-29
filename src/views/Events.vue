<template>
  <div>
    <v-card>
        <v-container
          fluid
          grid-list-lg
        >
          <v-layout row wrap>
            <v-flex xs12>
              <v-card color="blue" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Скандинавская ходьба</div>
                        <div class="caption">с инструктором</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="https://med-magazin.ua/images/articles.1513966656.1.b.jpg"
                      height="125px"
                      cover
                    ></v-img>
                  </v-flex>
                </v-layout>
                <v-divider light></v-divider>
                <v-flex xs12 text-xs-center>
                 <v-btn large>
                    <div class="mr-2">Получить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading mr-2">3</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>
            <v-flex xs12>
              <v-card color="blue" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Фитнес зарядка (утренняя)</div>
                        <div class="caption">на траве стадиона Старт</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="https://good-tips.pro/images/health/morning-workout.jpg"
                      height="125px"
                      cover
                    ></v-img>
                  </v-flex>
                </v-layout>
                <v-divider light></v-divider>
                <v-flex xs12 text-xs-center>
                 <v-btn large>
                    <div class="mr-2">Получить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading mr-2">3</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>

            <v-flex xs12>
              <v-card color="green" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Велопрокат</div>
                        <div class="caption">катание на ролика, катание на коньках</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="http://sportmagazin.net/upload/iblock/2ad/2adc3afeaf87e6e3b3b3434e3b8f8726.jpg"
                      height="125px"
                      cover
                    ></v-img>
                  </v-flex>
                </v-layout>
                <v-divider light></v-divider>
                <v-flex xs12 text-xs-center>
                 <v-btn large>
                    <div class="mr-2">Получить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading mr-2">1</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>

            <v-flex xs12>
              <v-card color="orange" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Эстафета</div>
                        <div class="caption">районная эстафета</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="https://bash.news/files/563FB20E786BB2F2.jpg"
                      height="125px"
                      cover
                    ></v-img>
                  </v-flex>
                </v-layout>
                <v-divider light></v-divider>
                <v-flex xs12 text-xs-center>
                 <v-btn large>
                    <div class="mr-2">Получить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading mr-2">100</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
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
  
</style>
