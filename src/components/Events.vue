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
  import axios from 'axios'

  export default {
    data () {
      return {
        events: null
      }
    },
    created() {
      this.getEvents()
    },
    methods: {
      getEvents() {
        axios.get('http://84.201.164.253/api/v1/events', {})
                .then(response => {
                  this.events = response.data.events
                })
      }
    }
  }
</script>

<style>

</style>

<style>

</style>
