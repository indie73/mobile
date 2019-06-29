<template>
  <div>
    <router-link :to="'add'" class="v-btn v-btn--floating v-btn--fixed v-btn--right v-btn--top theme--dark green add-btn" >
      <div class="v-btn__content">
        <v-icon dark>add</v-icon>
      </div>
    </router-link>
    <v-flex goals-header>
      <v-avatar
              :size="48"
              color="grey lighten-4"
      >
        <v-badge right
               color="green">
          <template v-slot:badge>
            <span>315</span>
          </template>
          <img src="https://vuetifyjs.com/apple-touch-icon-180x180.png" alt="avatar">
        </v-badge>
      </v-avatar>
      <div class="goals-header__name">
        Вася
      </div>
    </v-flex>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <v-card>
          <v-list two-line subheader>
            <v-subheader>Текущие</v-subheader>

            <v-list-tile
                    v-for="item in current"
                    :key="item.id"
                    avatar
                    @click=""
            >
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>

              <v-list-tile-action>
                <v-list-tile-sub-title>{{ item.current }} / {{ item.target }}</v-list-tile-sub-title>
              </v-list-tile-action>
            </v-list-tile>

            <v-divider></v-divider>
            <v-subheader>Выполненные</v-subheader>

            <v-list-tile
                    v-for="item in performed"
                    :key="item.id"
                    avatar
                    @click=""
            >
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>

              <v-list-tile-action>
                <v-list-tile-sub-title>
                  <v-icon>check</v-icon>
                </v-list-tile-sub-title>
              </v-list-tile-action>
            </v-list-tile>
          </v-list>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  export default {
    data: () => ({
      current: [
        {
          id: 1,
          title: 'Шаги',
          current: 3548,
          target: 5000,
          ball: 1,
          type: 0,
        },
        {
          id: 2,
          title: 'Сон(ч)',
          current: 5,
          target: 7,
          ball: 1,
          type: 0,
        },
        {
          id: 3,
          title: 'Использование смартфона(ч)',
          current: '1:19',
          target: '2',
          ball: 1,
          type: 1,
        },
        {
          id: 4,
          title: 'Шаги',
          current: 3548,
          target: 5000,
          ball: 1,
          type: 0,
        },
        {
          id: 5,
          title: 'Сон(ч)',
          current: 5,
          target: 7,
          ball: 1,
          type: 0,
        },
        {
          id: 6,
          title: 'Использование смартфона(ч)',
          current: '1:19',
          target: '2',
          ball: 1,
          type: 1,
        },
      ],
      performed: [
        {
          id: 7,
          title: 'Шаги',
          current: 3548,
          target: 5000,
          ball: 1,
          type: 0,
        },
        {
          id: 8,
          title: 'Сон(ч)',
          current: 5,
          target: 7,
          ball: 1,
          type: 0,
        },
        {
          id: 9,
          title: 'Использование смартфона(ч)',
          current: '1:19',
          target: '2',
          ball: 1,
          type: 1,
        },
      ],
    })
  }
</script>

<style>
  .v-list__tile__sub-title {
    text-align: right;
  }

  .goals-header {
    padding: 20px;
    text-align: center;
    background: #fff;
  }

  .goals-header .v-badge {
    width: 100%;
    height: 100%;
  }

  .goals-header .v-badge__badge {
    top: -5px;
    left: 38px;
    right: auto;
    border-radius: 15px;
    padding: 0 8px;
    width: auto;
    min-width: 22px;
  }

  .goals-header__name {
    margin-top: 5px;
    font-weight: 700;
  }

  .v-btn--top:not(.v-btn--absolute) {
    top: 83px;
  }

  .add-btn .v-btn__content {
    width: auto;
    height: auto;
  }
</style>
