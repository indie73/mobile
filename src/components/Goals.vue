<template>
  <div>
    <router-link :to="'add'" class="v-btn v-btn--floating v-btn--small v-btn--absolute v-btn--right v-btn--top theme--dark green add-btn" >
      <div class="v-btn__content">
        <v-icon dark>add</v-icon>
      </div>
    </router-link>
    <v-flex goals-header>
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
                <v-list-tile-sub-title v-if="item.target">{{ item.current }} / {{ item.target }}</v-list-tile-sub-title>
              </v-list-tile-action>
              <div class="v-list__tile__heart">
                <v-icon>favorites</v-icon>
                <div class="v-list__tile__heart__count">+{{ item.ball }}</div>
              </div>
            </v-list-tile>

            <v-divider></v-divider>
            <v-subheader>Выполненные</v-subheader>

            <v-list-tile
                    class="is-checked"
                    v-for="item in performed"
                    :key="item.id"
                    avatar
                    @click=""
            >
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>

              <div class="v-list__tile__heart">
                <v-icon
                        color="green"
                >favorites</v-icon>
                <div class="v-list__tile__heart__count">+{{ item.ball }}</div>
              </div>
            </v-list-tile>
          </v-list>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import axios from 'axios'

  export default {
    data () {
      return {
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
				  ball: 2,
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
				  id: 3,
				  title: 'Участие в марафоне',
				  ball: 20,
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
      }
    },
    created() {
      // this.getGoals()
    },
    methods: {
      getGoals() {
        axios.get('http://84.201.164.253/api/v1/goals', {})
                .then(response => {
                  this.current = response.data.current
                  this.performed = response.data.performed
                })
      }
    }
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

  .v-btn--top.v-btn--absolute.v-btn--small {
    top: 165px;
  }

  .add-btn .v-btn__content {
    width: auto;
    height: auto;
  }

  .v-list__tile__heart {
    position: relative;
    overflow: hidden;
    margin-left: 15px;
    width: 30px;
  }

  .v-list__tile__heart .v-icon {
    display: block;
    font-size: 30px;
  }

  .v-list__tile__heart__count {
    position: absolute;
    left: 50%;
    top: 50%;
    margin-top: -1px;
    font-size: 11px;
    color: #fff;
    transform: translate3d(-50%, -50%, 0);
  }

  .is-checked .v-list__tile__title {
    text-decoration: line-through;
  }
</style>
