<template>
  <v-app>
    <v-toolbar id="header" app v-if="!['login'].includes($route.name)" >
      <router-link :to="'home'" v-if="['add'].includes($route.name)" class="btn-back">
        <v-icon>arrow_back</v-icon>
      </router-link>
      <v-flex text-xs-center>
        <v-toolbar-title>
          БЕГУ.ЖИВУ
        </v-toolbar-title>
      </v-flex>

    </v-toolbar>

    <div v-if="['login'].includes($route.name)" class="ScrollableWrapper" style="text-align: -webkit-left;">
      <router-view/>
    </div>
    <div v-else class="ScrollableWrapper" style="padding-top: 65px; padding-bottom: 65px;text-align: -webkit-left;">
      <router-view/>
    </div>

    <v-bottom-nav fixed absolute
                  :active.sync="bottomNav"
                  :value="true"
                  absolute
                  id="foooter"
                  v-if="!['login'].includes($route.name)"
    >
      <router-link :to="'home'" style="text-decoration: none;">
      <v-btn
              color="teal"
              flat
              value="recent"
      >
        <span>Цели</span>
        <v-icon>stars</v-icon>
      </v-btn>
      </router-link>

      <router-link :to="'events'" style="text-decoration: none;">
      <v-btn
              color="teal"
              flat
              value="favorites"
      >
        <span>Заработать</span>
        <v-icon>favorite</v-icon>
      </v-btn>
      </router-link>

      <router-link :to="'shop'" style="text-decoration: none;">
        <v-btn
                color="teal"
                flat
                value="nearby"
        >
          <span>Обменять</span>
          <v-icon>shopping_cart</v-icon>
        </v-btn>
      </router-link>
    </v-bottom-nav>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      //
    }
  }
}
</script>

<style>

  /*########### SCROLLING HANDLING ###########*/
  html {
    overflow: hidden;
    height: 100%;
  }
  body {
    box-sizing: border-box;
    overflow: hidden;
    height: 100%;
  }
  header,footer {
    overflow: hidden;
  }

  .ScrollableWrapper {
    overflow: scroll;
    -webkit-overflow-scrolling: touch; /*to make it smooth as native*/
  }
  /*########### CUSTOM STYLE ###########*/
  header {
    background-color: #008bd2;
    color: white;
    text-align: center;
    padding-top: 0px;
    margin: 0px;
    position: fixed;
    z-index: 1000;
    top: 0px;
    left: 0px;
    width: 100%;
  }
  .ScrollableWrapper {
    top: 0;
    left:0;
    right:0;
    bottom:0;
    position:absolute;
  }
  #foooter {
    position: fixed;
    bottom:0px;
    z-index: 1;
    overflow: auto;
    background-color: #ffffff;
    width:100%;
  }
  body {
    margin: 0px;
    padding: 0px;

  }

  .twenty {
    width: 20%;
  }

  .container-fluid {
    width: 100%;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
  }

  .btn-back {
    position: absolute;
    left: 15px;
    top: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 30px;
    height: 30px;
    text-decoration: none;
    transform: translateY(-50%);
  }

</style>
