<template>
  <div>
    <v-card>
        <v-container
          fluid
          grid-list-lg
        >
          <v-layout row wrap>
            <v-flex xs12
              v-for="item in events"
              :key="item.id"
            >
              <v-card :color="item.color" class="white--text">
                <v-layout row>
                  <v-flex xs7>
                    <v-card-title primary-title>
                      <div>
                        <div class="title mb-1">{{ item.title }}</div>
                        <div class="caption">{{ item.caption }}</div>
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
                    <div class="mr-2">Получить</div>
                    <v-icon color="red" class="mr-2">favorite</v-icon>
                    <span class="subheading">{{ item.ball }}</span>
                  </v-btn>
                  <v-btn>
                    <v-icon color="" class="mr-2">group_add</v-icon>
                    <v-icon color="red" class="">favorite</v-icon>
                    <span class="caption">x</span><span class="subheading">{{ item.factor }}</span>
                  </v-btn>
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
    data: () => ({
      events: [
        {
          id: 1,
          title: 'Скандинавская ходьба',
          caption: 'с инструктором',
          ball: 3,
          src: 'https://med-magazin.ua/images/articles.1513966656.1.b.jpg',
          color: 'blue',
          factor: 2
        },
        {
          id: 2,
          title: 'Фитнес зарядка (утренняя)',
          caption: 'на траве стадиона Старт',
          ball: 3,
          src: 'https://good-tips.pro/images/health/morning-workout.jpg',
          color: 'blue',
          factor: 2
        },
        {
          id: 3,
          title: 'Велопрокат',
          caption: 'катание на ролика, катание на коньках',
          ball: 1,
          src: 'http://sportmagazin.net/upload/iblock/2ad/2adc3afeaf87e6e3b3b3434e3b8f8726.jpg',
          color: 'green',
          factor: 2
        },
        {
          id: 4,
          title: 'Эстафета',
          caption: 'районная эстафета',
          ball: 100,
          src: 'https://bash.news/files/563FB20E786BB2F2.jpg',
          color: 'orange',
          factor: 2
        }
      ]
     })
  }
</script>

<style>
  
</style>
