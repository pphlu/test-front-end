<template>
  <div id="sidebar" class="sidebar">
    <img src="https://wordpress-540516-1768503.cloudwaysapps.com/wp-content/uploads/2021/05/expsystem.png" id="logo" style="display: none">
    <button v-on:click="SideClick('250px','none','unset','unset','inline-block')" class="btn" id="open">
      <b-icon icon="arrow-bar-right"></b-icon>
    </button>
    <button v-on:click="SideClick('60px','unset','none','none','none')" class="btn" id="close" style="display: none">
      <b-icon icon="arrow-bar-left"></b-icon>
    </button>
    <a href="dashboard" style="margin-top: 30px">
      <b-icon icon="grid"></b-icon>
      <span class="hide">Dashboard</span>
    </a>
    <a href="users">
      <b-icon icon="person"></b-icon>
      <span class="hide">Users</span>
    </a>
    <a href="setting">
      <b-icon icon="gear"></b-icon>
      <span class="hide">Setting</span>
    </a>
  </div>
</template>


<script>
import { BIcon, BIconArrowBarLeft, BIconArrowBarRight, BIconGrid , BIconPerson, BIconGear} from 'bootstrap-vue'

export default {
  components: {
    BIcon,
    BIconArrowBarLeft,
    BIconArrowBarRight,
    BIconGrid,
    BIconPerson,
    BIconGear
  },
  methods: {
    SideClick: function (width, open, close, logo, link) {
      document.getElementById("sidebar").style.width = width;
      document.getElementById("open").style.display = open;
      document.getElementById("close").style.display = close;
      document.getElementById("logo").style.display = logo;
      var x = document.getElementsByClassName("hide");
      var i;
      for (i = 0; i < x.length; i++) {
        x[i].style.display = link;
      }
    }
  }
}
</script>

<style scoped>
#sidebar {
  width: 60px;
}
.sidebar {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #ffffff;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
  box-shadow: 0 0 20px #c9c9c9;
}

.sidebar a {
  padding: 8px 8px 8px 15px;
  text-decoration: none;
  font-size: 20px;
  color: #111;
  display: block;
  transition: 0.3s;
}
.sidebar a:hover {
  border-left: 5px solid #466dff;
  color: #8e8e8e;
}

#logo {
    position: absolute;
    top: 20px;
    padding: 10px;
    width: 170px;
}

.btn {
  position: absolute;
  top: 30px;
  right: 10px;
  font-size: 20px;
}

.hide {
    display: none;
    position: absolute;
    margin-left: 20px;
}


@media screen and (max-height: 450px) {
  .sidebar {padding-top: 15px;}
  .sidebar a {font-size: 18px;}
}
</style>