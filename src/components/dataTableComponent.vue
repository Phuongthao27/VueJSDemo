<template>
<div>
  <div>{{selectedId}}</div> 
  <v-data-table
  @click:row="rowClick" item-key="name" single-select
      :headers="headers"
      :items="listData"
      :items-per-page="5"
      class="elevation-1"
  ></v-data-table>
</div>
</template>

<script>
export default {
  name : 'datatable',
  props: ['listData','searchData'],
  methods: {
    rowClick: function (item, row) {      
      row.select(true);
      this.selectedId=[item.name]
    }
  },
  data () {
    return {
      selectedId: [],
      headers: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Calories', value: 'calories' },
        { text: 'Fat (g)', value: 'fat' },
        { text: 'Carbs (g)', value: 'carbs' },
        { text: 'Protein (g)', value: 'protein' },
        { text: 'Iron (%)', value: 'iron' },
      ],

    }
  },
}
</script>