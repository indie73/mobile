<template>
  <div>
    <h1 class="container-fluid">Добавить цель</h1>
    <v-card class="add">
      <v-flex class="add__line">
        <v-select
                :items="['Шаги(+1)','Велосипед(+1)','Плавание(+1)','Фитнес(+3)']"
                label="Тип"
                hide-details
        ></v-select>
      </v-flex>
      <v-flex class="add__line">
        <v-text-field
                label="Количество"
                type="tel"
                hide-details
        ></v-text-field>
      </v-flex>
      <v-flex class="add__line">
        <router-link :to="'home'" class="v-btn theme--light">
          Добавить
        </router-link>
      </v-flex>
    </v-card>
  </div>
</template>
<script>
  export default {
    data() {
      return {
      }
    },
    methods: {
    }
  }
</script>

<style>
  .add {
    padding: 15px;
  }

  .add__line {
    text-align: right;
  }

  .add__line + .add__line {
    margin-top: 15px;
  }
</style>
