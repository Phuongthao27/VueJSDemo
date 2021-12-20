<template>
  <div id="div">
    <label> Tên <input class = "idInput" type = 'text' v-bind:value="searchInput"/></label>
  </div>
</template>
<script>
export default {
  name:'input',

  data:function (){
    return {
      searchInput:"",
    }
  }

}

</script>
<style>
.idInput{
  border: 1px black solid;
}
#div{
  margin: 20px 10px;
}
</style>