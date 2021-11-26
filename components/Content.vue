<template>
  <div class="content">
    <b-container class="py-5">
      <b-row class="py-5">
        <b-col>
          <b-card
            :title=title1
            :img-src=imageUrl1
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
            {{description1}}
            </b-card-text>
            <b-button href="#" variant="primary">Go somewhere</b-button>
          </b-card>
        </b-col>
        <b-col>
          <b-card
            :title=title2
            :img-src=imageUrl2
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
            {{description2}}
            </b-card-text>
            <b-button href="#" variant="primary">Go somewhere</b-button>
          </b-card>
        </b-col>
        <b-col>
          <b-card
            :title=title3
            :img-src=imageUrl3
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>
            {{description3}}
            </b-card-text>
            <b-button href="#" variant="primary">Go somewhere</b-button>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  props:{
    title1:{
      type:String,
      required:false
    },
    description1:{
      type:String,
      required:false
    },
    imageUrl1:{
      type:String,
      required:false  
    },
    title2:{
      type:String,
      required:false
    },
    description2:{
      type:String,
      required:false
    },
    imageUrl2:{
      type:String,
      required:false  
    },
    title3:{
      type:String,
      required:false
    },
    description3:{
      type:String,
      required:false
    },
    imageUrl3:{
      type:String,
      required:false  
    }
  }
}
</script>

<style scoped>
.content {
  margin-left: 59px;
}
</style>