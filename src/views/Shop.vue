<template>
  <div>
    <v-card>
        <v-container
          fluid
          grid-list-lg
        >
          <v-layout row wrap>
            <v-flex xs12>
              <v-card color="green" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">1 посещение врача</div>
                        <div class="caption">в платной клинике</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="data:image/jpeg;base64,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"
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
                    <span class="subheading mr-2">50</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>
            <v-flex xs12>
              <v-card color="blue" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">1 занятие фитнесом</div>
                        <div class="caption">в фитнес клубе ULTRA</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRkX9_ZRzxJwo83goX8vwLmPf6YCsIYA968mWq4zUDnWzjML_FZ"
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
                    <span class="subheading mr-2">50</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>

            <v-flex xs12>
              <v-card color="green" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Набор здорового питания</div>
                        <div class="caption">от Зеленая улица</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="http://i.otzovik.com/objects/b/310000/300455.png"
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
                    <span class="subheading mr-2">40</span></v-btn>
                </v-flex>
              </v-card>
            </v-flex>

            <v-flex xs12>
              <v-card color="orange" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title">Большая бутылка воды</div>
                        <div class="caption">Волжанка 20 л</div>
                      </div>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs5>
                    <v-img
                      src="https://ledniklive.ru/upload/resize_cache/iblock/23e/385_385_1/23ed8b682f193fd6dc2b152c0d06f289.jpg"
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
                    <span class="subheading mr-2">35</span></v-btn>
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
