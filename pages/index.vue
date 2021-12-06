<template> 
  <div>
    <div>
      <b-carousel
        id="carousel-no-animation"
        style="text-shadow: 0px 0px 2px #000"
        no-animation
        indicators
        img-width="1024"
        img-height="480"
      >
        <b-carousel-slide v-for="index in 3" :key="index"
          img-src="~static/img1.png"
        ></b-carousel-slide>
      </b-carousel>
    </div>
    <b-container class="py-3">
      <div class="btn-panel">
        <div class="btn-panel-inside">
          <b-button class="btn-filter" v-on:click="userFilterKey = 'hit'" :class="{ filteractive: userFilterKey == 'hit' }">
            <b-img src="~static/star1.png" class="btn-filter-img-active"></b-img>
            <b-img src="~static/lv1.png" class="btn-filter-img"></b-img>
            เกมยอดนิยม
          </b-button>
        </div>
        <div class="btn-panel-inside">
          <b-button class="btn-filter" v-on:click="userFilterKey = 'event'" :class="{ filteractive: userFilterKey == 'event' }">
            <b-img src="~static/star1.png" class="btn-filter-img-active"></b-img>
            <b-img src="~static/lv1.png" class="btn-filter-img"></b-img>
            กิจกรรม
          </b-button>
        </div>
        <div class="btn-panel-inside">
          <b-button class="btn-filter" v-on:click="userFilterKey = 'mission'" :class="{ filteractive: userFilterKey == 'mission' }">
            <b-img src="~static/star1.png" class="btn-filter-img-active"></b-img>
            <b-img src="~static/lv1.png" class="btn-filter-img"></b-img>
            ภารกิจ
          </b-button>
        </div>
        <div class="btn-panel-inside">
          <b-button class="btn-filter" v-on:click="userFilterKey = 'community'" :class="{ filteractive: userFilterKey == 'community' }">
            <b-img src="~static/star1.png" class="btn-filter-img-active"></b-img>
            <b-img src="~static/lv1.png" class="btn-filter-img"></b-img>
            คอมมูนิตี้
          </b-button>
        </div>
      </div>
    </b-container>
    <b-container>
      <b-row>
        <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==0" sm="3" class="padding5">
          <Cardgame
            :gamename=game.name
            imgheight="200px"
          />
          <b-img src="~static/hot-diamond.png" class="game-new"></b-img>
          <p class="game-new-text">ใหม่</p>
        </b-col>
        <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==1 || id==2" xs class="padding5">
          <Cardgame
            :gamename=game.name
            imgheight="200px"
          />
        </b-col>
        <div class="w-100"></div>
        <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==3 || id==4" xs class="padding5">
          <Cardgame
            :gamename=game.name
            imgheight="200px"
          />
        </b-col>
        <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==5" sm class="padding5">
          <Cardgame
            :gamename=game.name
            imgheight="200px"
          />
        </b-col>
      </b-row>
      <b-row>
        <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==6" sm="5" class="padding5">
          <Cardgame
            :gamename=game.name
            imgheight="212px"
          />
          <b-img src="~static/hot-diamond.png" class="game-new"></b-img>
          <p class="game-new-text">ใหม่</p>
        </b-col>
        <b-col sm class="no-padding">
          <b-row>
            <b-col sm="12" class="no-padding">
              <b-row>
                <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==7 || id==8" xs class="padding5">
                  <Cardgame
                    :gamename=game.name
                    imgheight="100px"
                  />
                </b-col>
              </b-row>
            </b-col>
            <b-col sm="12" class="no-padding">
              <b-row>
                <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==9 || id==10" xs class="padding5">
                  <Cardgame
                    :gamename=game.name
                    imgheight="100px"
                  />
                </b-col>
              </b-row>
            </b-col>
          </b-row>
        </b-col>
        <b-col sm class="no-padding">
          <b-row>
            <b-col v-for="(game, id) in userFilter" :key="id" v-if="id==11 || id==12" sm="12" class="padding5">
              <Cardgame
                :gamename=game.name
                imgheight="100px"
              />
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-container>

    <b-container>
      <p style="margin: 10px 15px 0; color: white;">โปรโมชั่นประจำเดือน</p>
      <div class="div-slider">
        <div class="div-slider-inside" v-for="index in 6" :key="index">
          <b-img src="~static/img2.png" style="width:300px"></b-img>
          <div class="sale-price">
            <span class="sale-price-1">พิเศษ</span>
            <span class="sale-price-2">250 บาท</span>
            <span class="sale-price-3">500 บาท</span>
          </div>
          <b-img src="~static/pngfind.png" class="sale"></b-img>
          <p class="sale-text">เกมนี้ลด 50%</p>
          <b-button pill class="sale-btn">ซื้อ</b-button>
        </div>      
      </div>
    </b-container>

    <b-container class="py-3">
      <b-row>
        <b-col lg style="padding: 10px">
          <div class="gradient win">
            <p>ผู้ชนะทัวร์นาเมนท์ 10 ลำดับล่าสุด</p>
            <div class="win-inside">
              <div class="win-user" v-for="(item, id) in items" :key="id">
                <b-row>
                  <b-col cols="3">
                    <span class="round">{{ id+1 }}</span>
                    <b-img src="~static/img2.png" class="avatar"></b-img>
                  </b-col>
                  <b-col style="padding: 0 0 0 20px">
                    <h6>{{ item.user }}</h6>
                    <b-img src="~static/credit.png" style="width:20px"></b-img>
                    <span class="text-gold">ได้รับตำลึงทอง {{ item.gold }}</span>
                  </b-col>
                </b-row>
              </div>
            </div>
          </div>
        </b-col>
        <b-col lg style="padding: 10px">
          <div class="rewards">
            <b-row class="padding">
              <b-col sm class="no-padding">
                <div class="in-middle">
                  <div class="text-daily">
                    DAILY<br>
                    REWARDS
                  </div>
                </div>              
              </b-col>
              <b-col sm class="no-padding" style="text-align: center">
                <b-img src="~static/Frame.png" class="diamond"></b-img>
                <div class="text-diamond">x50 diamonds</div>
              </b-col>
              <b-col sm class="no-padding">
                <div class="in-middle">
                  <div class="text-time">
                    <div class="div-dot">
                      <span class="dot" style="background-color: #62dbfe"></span>
                      <span class="dot"></span>
                      <span class="dot"></span>
                    </div>
                    TIMES LEFT
                    <h4>10:00:22</h4>
                  </div>     
                </div>
              </b-col>
            </b-row>
          </div>
          <div style="padding-top: 3rem">
            <div class="invite">ชวนเพื่อนมาเล่น <span class="invite-text">เพื่อรับเพชร</span></div>
            <div class="social-image">
              <div class="social-panel">
                <div>
                  <span class="social facebook"><b-icon icon="facebook"></b-icon></span>
                  <span class="social twitter"><b-icon icon="twitter"></b-icon></span>
                  <span class="social instagram"><b-icon icon="instagram"></b-icon></span>
                </div>
                <div>
                  <span class="social youtube"><b-icon icon="youtube"></b-icon></span>
                  <span class="social google"><b-icon icon="google"></b-icon></span>
                  <span class="social github"><b-icon icon="github"></b-icon></span>
                </div>
              </div>
            </div>
          </div>
        </b-col>
        <b-col lg style="padding: 10px">
          <div class="h-100 contact">
            <div class="gradient title-contact">CONTACT US</div>
            <div class="body-contact">
              <form>
                <label for="name">Name</label>
                <input type="text" id="name" name="name">
                <label for="email">Email</label>
                <input type="text" id="email" name="email">
                <label for="message" style="padding: 10px 10px 0">Message</label>
                <textarea id="message" name="message"></textarea>
                <b-button block class="btn-contact">ส่งข้อความ</b-button>
              </form>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <div class="line"></div>
  </div>
</template>

<script>
import Cardgame from '@/components/Cardgame'
import { BIcon, BIconFacebook, BIconTwitter, BIconInstagram, BIconYoutube, BIconGoogle, BIconGithub} from 'bootstrap-vue'

export default {
  components:{
    Cardgame,
    BIcon,
    BIconFacebook,
    BIconTwitter,
    BIconInstagram,
    BIconYoutube,
    BIconGoogle,
    BIconGithub
  },
  data() {
    return {
      userFilterKey: 'hit',
      games: [
        { name: 'Hit 1', category: 'hit' },
        { name: 'Hit 2', category: 'hit' },
        { name: 'Hit 3', category: 'hit' },
        { name: 'Hit 4', category: 'hit' },
        { name: 'Hit 5', category: 'hit' },
        { name: 'Hit 6', category: 'hit' },
        { name: 'Hit 7', category: 'hit' },
        { name: 'Hit 8', category: 'hit' },
        { name: 'Hit 9', category: 'hit' },
        { name: 'Hit 10', category: 'hit' },
        { name: 'Hit 11', category: 'hit' },
        { name: 'Hit 12', category: 'hit' },
        { name: 'Hit 13', category: 'hit' },
        { name: 'Event 1', category: 'event' },
        { name: 'Event 2', category: 'event' },
        { name: 'Event 3', category: 'event' },
        { name: 'Event 4', category: 'event' },
        { name: 'Event 5', category: 'event' },
        { name: 'Event 6', category: 'event' },
        { name: 'Event 7', category: 'event' },
        { name: 'Event 8', category: 'event' },
        { name: 'Event 9', category: 'event' },
        { name: 'Event 10', category: 'event' },
        { name: 'Event 11', category: 'event' },
        { name: 'Event 12', category: 'event' },
        { name: 'Event 13', category: 'event' },
        { name: 'Mission 1', category: 'mission' },
        { name: 'Mission 2', category: 'mission' },
        { name: 'Mission 3', category: 'mission' },
        { name: 'Mission 4', category: 'mission' },
        { name: 'Mission 5', category: 'mission' },
        { name: 'Mission 6', category: 'mission' },
        { name: 'Mission 7', category: 'mission' },
        { name: 'Mission 8', category: 'mission' },
        { name: 'Mission 9', category: 'mission' },
        { name: 'Mission 10', category: 'mission' },
        { name: 'Mission 11', category: 'mission' },
        { name: 'Mission 12', category: 'mission' },
        { name: 'Mission 13', category: 'mission' },
        { name: 'Community 1', category: 'community' },
        { name: 'Community 2', category: 'community' },
        { name: 'Community 3', category: 'community' },
        { name: 'Community 4', category: 'community' },
        { name: 'Community 5', category: 'community' },
        { name: 'Community 6', category: 'community' },
        { name: 'Community 7', category: 'community' },
        { name: 'Community 8', category: 'community' },
        { name: 'Community 9', category: 'community' },
        { name: 'Community 10', category: 'community' },
        { name: 'Community 11', category: 'community' },
        { name: 'Community 12', category: 'community' },
        { name: 'Community 13', category: 'community' }
      ],
      isHovered: false,
      items: [
        { user:"UserName 1", gold:"100K" },
        { user:"UserName 2", gold:"90K" },
        { user:"UserName 3", gold:"88K" },
        { user:"UserName 4", gold:"56K" },
        { user:"UserName 5", gold:"50K" },
        { user:"UserName 6", gold:"43K" },
        { user:"UserName 7", gold:"39K" },
        { user:"UserName 8", gold:"30K" },
        { user:"UserName 9", gold:"25K" },
        { user:"UserName 10", gold:"16K" }
      ]
    }
  },
  computed: {
  	userFilter() {
    	return this[this.userFilterKey]
    },
    hit() {
      return this.games.filter((game) => game.category == 'hit')
    },
    event() {
      return this.games.filter((game) => game.category == 'event')
    },
    mission() {
      return this.games.filter((game) => game.category == 'mission')
    },
    community() {
      return this.games.filter((game) => game.category == 'community')
    }
  },
  methods: {
    prev() {
      this.$refs.myCarousel.prev()
    },
    next() {
      this.$refs.myCarousel.next()
    },
    handleHover(hovered) {
      this.isHovered = hovered
    }
  }
}
</script>

<style>
body {
  background-image: linear-gradient(to bottom right, #5b00a1, #9923b7, #5b00a1);
}
.carousel-indicators li {
  width: 10px !important;
  height: 10px !important;
  border-radius: 50% !important;
  background-color: #ffcc00 !important;
  opacity: 1 !important;
}
.carousel-indicators .active {
  width: 20px !important;
  height: 10px !important;
  border: none !important;
  border-radius: 20px !important;
  background-color: #ff07e6 !important;
  margin-top: 10px !important;
}
@media only screen and (max-width: 700px) {
  img.img-fluid.w-100.d-block {
    height: 350px;
    object-fit: cover;
  }
}
.no-padding {
  padding: 0;
}
.padding5{
  padding: 5px;
}
.row {
  margin: 0;
}
img {
  width: 100%;
}
@media (min-width: 1200px) {
  .container, .container-sm, .container-md, .container-lg, .container-xl {
    max-width: 1300px !important;
  }
}
@media only screen and (max-width: 575px) {
  .padding {
    padding: 3em 0;
  }
}

/* --- show game in paragraph 1 --- */
.btn-panel {
  max-width:700px;
  padding: 20px 0 0;
  margin: 0 auto;
  overflow-x: auto;
}
.btn-panel::-webkit-scrollbar {
  height: 7px;
}
.btn-panel::-webkit-scrollbar-track {
  background-color: transparent;
}
.btn-panel::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #00000057;
}
.btn-panel::-webkit-scrollbar-button:start {
  width: 30%;
}
.btn-panel::-webkit-scrollbar-button:end {
  width: 30%;
}
.btn-panel-inside {
  display: table-cell;
  position: relative;
  padding: 0 5px 10px;
}
.btn-filter {
  width: 160px;
  border: 2px solid #6b6b6b;
  border-radius: 20px;
  outline: none;
  padding: 5px 0;
  background-image: linear-gradient(to bottom right, #bababa, #ececec, #ececec, #bababa);
  cursor: pointer;
  font-size: 18px;
  text-shadow: 0 0 2px #000000;
}
.filteractive {
  background-image: linear-gradient(to bottom right, #7c00ca, #ffd200, #ffd200, #ff00e4);
  color: black !important;
  border-top: 2px solid #ffb400 !important;
  border: none;
  text-shadow: none;
}
.btn-filter-img {
  width: 25px;
  margin-right: 7px;
}
.btn-filter-img-active {
  width: 25px;
  left: 5px;
  top: -8px;
  position: absolute;
  opacity:0;
}
.btn-filter.filteractive .btn-filter-img-active {
  opacity: 1;
}
.btn-filter.filteractive .btn-filter-img {
  display: none;
}
.w-100 {
  display: none;
}
.game-new {
  position: absolute;
  top: 0;
  left: 0;
  padding: 5px;
  width: 70px;
}
.game-new-text {
  position: absolute;
  top: 18px;
  left: 12px;
  transform: rotate(310deg);
  font-size: 0.8em;
  font-weight: bold;
}
@media only screen and (max-width: 575px) {
  .w-100 {
    display: block;
  }
}
@media (min-width: 576px) {
  .col-sm-5 {
    max-width: 40%;
  }
}

/* --- slider in paragraph 2 --- */
.div-slider {
  width: 100%;
  padding-bottom: 20px;
  overflow-x: auto;
  overflow-y: hidden;
}
.div-slider::-webkit-scrollbar {
  height: 15px;
}
.div-slider::-webkit-scrollbar-track {
  background-image: radial-gradient(circle,#ffcc00,#ffcc00,#ffcc00,#ffcc00,transparent,transparent,transparent,transparent,transparent);
  background-size: 13px;
}
.div-slider::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #ff07e6;
  border: 3px solid transparent;
  background-clip: content-box;
}
.div-slider::-webkit-scrollbar-button:start {
  width: 46%;
}
.div-slider::-webkit-scrollbar-button:end {
  width: 46%;
}
.div-slider-inside {
  display: table-cell;
  position: relative;
  padding: 10px;
}
.sale-price {
  width: fit-content;
  padding: 0 25px;
  background-color: #000000d4;
  border-style: solid;
  border-width: 3px;
  border-image: linear-gradient(180deg, rgb(98,0,187), rgb(255,0,235)) 1;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.sale-price-1 {
  color: #ffcc00;
  font-size: 0.8em;
}
.sale-price-2 {
  color: #ffcc00;
  font-size: 1.2em;
  font-weight: bold;
}
.sale-price-3 {
  color: red;
  font-size: 0.9em;
  text-decoration: line-through;
  display: block;
}
.sale {
  position: absolute;
  top: 45%;
  left: 28%;
  transform: translate(-50%, -50%);
  width: 140px;
}
.sale-text {
  position: absolute;
  top: 33%;
  left: 16%;
  -ms-transform: rotate(340deg);
  transform: rotate(340deg);
  font-size: 0.8em;
  font-weight: bold;
}
.sale-btn {
  width: 120px;
  padding: 3px 0;
  font-size: 1em;
  font-weight: bold;
  text-shadow: 0 0 3px #3c0068;
  border: solid 2px transparent;
  border-bottom: none;
  background-image: linear-gradient(rgba(255, 255, 255, 0), rgba(255, 255, 255, 0)), linear-gradient(180deg, #ffd236, #ff48fa);
  background-origin: border-box;
  background-clip: content-box, border-box;
  box-shadow: inset 2px 1000px 1px #811ff1, 0 0 5px black;
  position: absolute;
  top: 95%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* --- show win user in paragraph 3.1 --- */
.win {
  border-radius: 5px;
}
.win p {
  text-align: center;
  font-size: 1em;
  font-weight: bold;
  padding: 10px 0;
  margin: 0;
}
.win-inside {
  overflow-y: scroll;
  height: 370px;
  padding: 0 5px 0 15px;
  margin-right: 5px;
}
.win-inside::-webkit-scrollbar-track {
  background-color: #404040;
  margin: 5px 0;
  border-radius: 10px;
}
.win-inside::-webkit-scrollbar {
  width: 8px;
}
.win-inside::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #a454ff;
}
.win-user {
  padding: 10px;
  color: white;
  background-color: #00000096;
  margin: 5px 0;
  border-radius: 5px;
}
.win-user h6 {
  margin: 0;
}
.round {
  height: 25px;
  width: 25px;
  background-color: #ffcc00;
  border-radius: 50%;
  display: inline-block;
  text-align: center;
  font-weight: 500;
  position: absolute;
  left: 0;
  margin-top: -6px;
  color: black;
}
.avatar {
  width: 50px;
  height: 50px;
  border-radius: 5px;
}
.text-gold {
  font-size: 1em;
}
@media only screen and (max-width: 1199px) {
  .win-inside {
    height: 350px;
  }
  .text-gold {
    font-size: 0.9em !important;
  }
}
@media only screen and (max-width: 390px) {
  .text-gold {
    font-size: 0.7em !important;
  }
}

/* --- show reward in paragraph 3.2 --- */
.rewards {
  background-image: url("~static/img3.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: white;
}
.text-daily {
  font-size: 1.4em;
  line-height: 1em;
  font-weight: bold;
  text-align: right;
  padding-right: 14px;
  background: linear-gradient(280deg,transparent 5%, #e10059 10%, transparent 9%),linear-gradient(-260deg
  ,transparent 90%, #e10059 10%, transparent 94%);
}
.text-time {
  font-size: 0.7em;
  line-height: 0.3em;
}
.text-time h4 {
  margin: 0;
}
.div-dot {
  background-color: black;
  width: fit-content;
  border-radius: 5px;
  line-height: 0;
  padding: 2px;
  margin-bottom: 7px;
}
.dot {
  height: 5px;
  width: 25px;
  background-color: #4b585c;
  border-radius: 5px;
  display: inline-block;
}
.diamond {
  width: 100%;
  padding: 10% 20%;
}
.text-diamond {
  width: 70%;
  background-color: #00000099;
  border-radius: 20px;
  color: white;
  font-size: 0.8em;
  text-align: center;
  position: absolute;
  top: 85%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.in-middle {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.invite {
  width: fit-content;
  padding: 5px 15px;
  color: white;
  background-color: #000000d4;
  border-style: solid;
  border-width: 3px;
  border-image: linear-gradient(180deg, rgb(161,0,201), rgb(255,43,238)) 1;
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
}
.invite-text {
  text-align: center;
}
.social-image {
  background-image: url("~static/img2.png");
  background-color: black;
  height: 260px;
  background-position: top center;
  background-repeat: no-repeat;
  background-size: cover;
  border-radius: 5px;
}
.social-panel {
  position: absolute;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: fit-content;
}
.social {
  height: 50px;
  width: 50px;
  border-radius: 50%;
  display: inline-block;
  background-color: #bbb;
  color: white;
  font-size: 30px;
  text-align: center;
  margin: 5px 10px;
}
.facebook {
  background-color: #3b5998;
}
.twitter {
  background-color: #00acee;
}
.instagram {
  background-image: linear-gradient(to top right, #fccc63, #e95950, #bc2a8d, #8a3ab9, #4c68d7);
}
.youtube {
  background-color: #FF0000;
}
.google {
  background-color: #4285F4;
}
.github {
  background-color: #333;
}
@media only screen and (max-width: 1199px) {
  .text-daily {
    font-size: 1em;
  }
  .diamond {
    padding: 10% 15%;
  }
  .text-diamond {
    font-size: 0.65em;
  }
}
@media only screen and (max-width: 991px) {
  .text-daily {
    font-size: 1.5em;
  }
  .diamond {
    padding: 10% 20%;
  }
  .text-diamond {
    font-size: 0.8em;
  }
}
@media only screen and (max-width: 575px) {
  .diamond {
    width: 60%;
  }
  .text-diamond {
    top: 75%;
    width: fit-content;
    padding: 0 5px;
    font-size: 1em;
  }
  .invite-text {
    display: block;
  }
  .social-image {
    height: 230px;
  }
  .social-panel {
    top: 85%;
  }
}
@media only screen and (max-width: 480px) {
  .diamond {
    padding: 10% 20% 15%;
  }
  .text-diamond {
    top: 65%;
    font-size: 1em;
  }
}
@media only screen and (max-width: 380px) {
  .diamond {
    padding: 15%;
  }
  .text-diamond {
    top: 70%;
  }
}

/* --- contact us in paragraph 3.3 --- */
.gradient {
  background-image: linear-gradient(#ff5ed7, #ffcc00);
}
.contact {
  background-color: #3a3a3a;
  border-radius: 10px;
}
.title-contact {
  padding: 10px;
  font-size: 1em;
  font-weight: bold;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}
.body-contact {
  padding: 0 15px 20px;
}
.btn-contact {
  background-color: #a454ff;
  border: none;
  margin-top: 10px;
}
input[type=text] {
  width: 100%;
  padding: 10px 20px;
  margin-top: 30px;
  box-sizing: border-box;
  border: none;
  outline: none;
  border-radius: 7px;
  background-color: #747474;
  color: white;
}
input[type=text]:focus {
  border: 2px solid #ffcc00;
}
textarea {
  width: 100%;
  height: 100px;
  padding: 12px 20px;
  margin-top: 30px;
  box-sizing: border-box;
  border: none;
  outline: none;
  border-radius: 7px;
  background-color: #747474;
  color: white;
  resize: none;
}
label {
  position: absolute;
  padding: 17px 10px 0;
  color: white;
}

.line {
  height: 7px;
  background-image: linear-gradient(to right, #ffe373, #a837ff);
  margin-bottom: 30px;
}
</style>