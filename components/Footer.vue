<template>
  <div class="footer">
    <b-container>
      <button v-on:click="ScrollToTop()" class="gototop">
        <b-icon icon="chevron-up" style="margin:0"></b-icon>
      </button>
      <p class="py-3">xx/xx xxxxxxxxxx xxxxx xxx Fl., xxxxxxxx Rd. xxxxx xxxxxx, xxxxxxxx, Bangkok xxxxx</p>
      <b-row>
        <b-col>
          <b-icon icon="telephone-fill"></b-icon><span>xx-xxxxxxx</span>
        </b-col>
        <b-col>
          <b-icon icon="envelope-fill"></b-icon><span>xxxxxxxx@xxxxxx.xxx</span>
        </b-col>
        <b-col>
          <b-icon icon="facebook"></b-icon><span>xxxxxxx</span>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import { BIcon, BIconChevronUp, BIconTelephoneFill, BIconEnvelopeFill, BIconFacebook} from 'bootstrap-vue'

export default {
  components: {
    BIcon,
    BIconChevronUp,
    BIconTelephoneFill,
    BIconEnvelopeFill,
    BIconFacebook
  },
  methods: {
    ScrollToTop: function () {
      window.scrollTo({
        top: 0,
        left: 0,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style scoped>
.footer {
  margin-left: 60px;
  text-align: center;
  padding: 30px 50px;
  background-color: #466dff;
  color: #ffffff;
}
.gototop {
  height: 50px;
  width: 50px;
  border: 2px solid #ffffff;
  border-radius: 50%;
  background-color: transparent;
  color: #ffffff;
  font-size: 30px;
  line-height: 25px;
  font-weight: bold;
}
.b-icon.bi {
  font-size: 30px;
  margin-right: 10px;
}
</style>