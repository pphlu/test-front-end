<template>
  <b-card
    overlay
    img-src="~static/img4.png"
    :img-height=imgheight
  >
    <b-img src="~static/star1.png" class="star"></b-img>
    <b-card-text>
      {{ gamename }}
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  props:{
    gamename:{
      type:String,
      required:true
    },
    imgheight:{
      type:String,
      required:true  
    }
  }
}
</script>

<style scoped>
.card {
  border: none;
}
.card-text {
  position: absolute;
  bottom: 0;
  width: 100%;
  background-color: #000000cc;
  text-align: center;
  font-size: 18px;
  line-height: 40px;
  color: #ffffff;
  border-bottom-left-radius: 3px;
  border-bottom-right-radius: 3px;
}
.card-img-overlay {
  padding: 0;
}
.star {
  width: 30px;
  right: 0;
  position: absolute;
  margin: 10px;
  opacity:0;
  transition: .5s ease;
}
.card:hover .star {
  opacity: 1;
}
</style>