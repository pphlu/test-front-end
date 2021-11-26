<template>
  <div class="header" :style="{ backgroundImage: `url(${backgroundUrl})` }">
    <b-container style="padding: 3%">
      <b-row>
        <b-col>
          <h1>{{ title }}</h1>
          <p>{{ description }}</p>
        </b-col>
        <b-col>
          <img :src="imageUrl" style="width:300px">
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  props:{
    backgroundUrl:{
      type:String,
      required:true
    },
    title:{
      type:String,
      required:true
    },
    description:{
      type:String,
      required:true
    },
    imageUrl:{
      type:String,
      required:true  
    }
  }
}
</script>

<style scoped>
.header {
  margin-left: 59px;
  text-align: center;
  background-repeat: no-repeat;
  background-size: 100%;
}
.col {
  margin: auto auto;
}
h1 {
  font-size: 65px
}
</style>