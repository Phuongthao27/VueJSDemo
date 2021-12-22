<template>
  <v-app id="inspire">
    <v-navigation-drawer
        v-model="drawer"
        app
    >
      <menuComponent></menuComponent>
      <!--  -->
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>List Student</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <div class = 'two-part'>
        <div class = 'two-part-compo'>
          <h1>search:{{search}}</h1>

          <label> Tên <input style="border: black solid 0.5px" class = "idInput" type = 'text' v-model="search"/></label>
        </div>
        <div class = 'two-part-compo'>

        </div>
      </div>
      <div class = 'two-part'>


        <datatable  v-bind:list-data ="searchData "></datatable>
        <testCheckbox/>

      </div>

    </v-main>
  </v-app>
</template>

<script>

import menuComponent from "@/components/menuComponent";
import datatable from "@/components/dataTableComponent";
import testCheckbox from "./components/testCheckbox.vue"
export default {
  props : ["searchInput"],
  data: () => ({
    drawer: null ,

    search : "",
    listDataSearch :[],
    listData : [
      {
        name: 'Frozen Yogurt',
        calories: 159,
        fat: 6.0,
        carbs: 24,
        protein: 4.0,
        iron: '1%',
      },
      {
        name: 'Ice cream sandwich',
        calories: 237,
        fat: 9.0,
        carbs: 37,
        protein: 4.3,
        iron: '1%',
      },
      {
        name: 'Eclair',
        calories: 262,
        fat: 16.0,
        carbs: 23,
        protein: 6.0,
        iron: '7%',
      },
    ]


  }),
  computed :{
    searchData :function (){
      return this.listData.filter(listData => listData.name.includes(this.search));
    },
  },
  components :{

    menuComponent,
    datatable,
    testCheckbox,
  }
}
</script>
<style>
.two-part{
  display: block;
  background: antiquewhite;
}
.two-part-compo{
  display: inline-block;
}
</style>