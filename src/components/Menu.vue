<template>
  <div class="navbar">
    <div class="component">
      <!-- Start Nav Structure -->
      <button class="cn-button" v-on:click="toggle" id="cn-button">+</button>
      <div class="cn-wrapper" id="cn-wrapper">
        <ul>
          <li>
            <a href="#/firstPageEditor">
              <span class="cm-icon icon-mainpage"></span>
            </a>
          </li>
          <li>
            <a href="#">
              <span class="cm-icon icon-calender"></span>
            </a>
          </li>
          <li>
            <a href="#">
              <span class="cm-icon icon-files"></span>
            </a>
          </li>
          <li>
            <a href="#">
              <span class="cm-icon icon-settings"></span>
            </a>
          </li>
          <li>
            <a href="#">
              <span class="cm-icon icon-settings"></span>
            </a>
          </li>
        </ul>
      </div>
      <div id="cn-overlay" class="cn-overlay"></div>
      <!-- End Nav Structure -->
    </div>
  </div>
</template>

<script>
export default {
  name: "menu",
  props: {
    title: String
  },
  data() {
    return {
      collapsed: true
    };
  },
  methods: {
    toggle() {
      //console.log(this.collapsed);
      this.collapsed = !this.collapsed;
      var wrapper = this.$el.querySelector(".cn-wrapper");
     // console.log(wrapper);

      if (!this.collapsed) {
        wrapper.classList.add("opened-nav");
        //openNav();
      } else {
       // console.log("remove");
        wrapper.classList.remove("opened-nav");
        //closeNav();
      }
    }
  }
};
</script>

<style lang="css" scoped>
/*
*To-do: Move out to seperate file
*/
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
.cn-wrapper {
  font-size: 1em;
  width: 26em;
  height: 26em;
  overflow: hidden;
  position: fixed;
  z-index: 10;
  bottom: -13em;
  left: 50%;
  border-radius: 50%;
  margin-left: -13em;
  -webkit-transform: scale(0.1);
  -ms-transform: scale(0.1);
  -moz-transform: scale(0.1);
  transform: scale(0.1);
  pointer-events: none;
  -webkit-transition: all 0.3s ease;
  -moz-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
.cn-button {
  border: none;
  background: none;
  color: #f06060;
  text-align: center;
  font-size: 1.8em;
  padding-bottom: 1em;
  height: 3.5em;
  width: 3.5em;
  background-color: #fff;
  position: fixed;
  left: 50%;
  margin-left: -1.75em;
  bottom: -1.75em;
  border-radius: 50%;
  cursor: pointer;
  z-index: 11;
}
.cn-wrapper li {
  position: absolute;
  font-size: 1.5em;
  width: 10em;
  height: 10em;
  -webkit-transform-origin: 100% 100%;
  -moz-transform-origin: 100% 100%;
  -ms-transform-origin: 100% 100%;
  transform-origin: 100% 100%;
  overflow: hidden;
  left: 50%;
  top: 50%;
  margin-top: -1.3em;
  margin-left: -10em;
  -webkit-transition: border 0.3s ease;
  -moz-transition: border 0.3s ease;
  transition: border 0.3s ease;
}
.cn-wrapper li a {
  display: block;
  font-size: 1.18em;
  height: 12.7em;
  width: 14.5em;
  position: absolute;
  bottom: -7.25em;
  right: -7.25em;
  border-radius: 50%;
  text-decoration: none;
  color: #fff;
  padding-top: 1.8em;
  text-align: center;
  -webkit-transform: skew(-50deg) rotate(-70deg) scale(1);
  -ms-transform: skew(-50deg) rotate(-70deg) scale(1);
  -moz-transform: skew(-50deg) rotate(-70deg) scale(1);
  transform: skew(-50deg) rotate(-70deg) scale(1);
  -webkit-backface-visibility: hidden;
  -webkit-transition: opacity 0.3s, color 0.3s;
  -moz-transition: opacity 0.3s, color 0.3s;
  transition: opacity 0.3s, color 0.3s;
}
.cn-wrapper li a span {
  font-size: 1.1em;
  opacity: 0.7;
}

/* for a central angle x, the list items must be skewed by 90-x degrees
in our case x=40deg so skew angle is 50deg
items should be rotated by x, minus (sum of angles - 180)2s (for this demo) */

.cn-wrapper li:first-child {
  -webkit-transform: rotate(-10deg) skew(50deg);
  -ms-transform: rotate(-10deg) skew(50deg);
  -moz-transform: rotate(-10deg) skew(50deg);
  transform: rotate(-10deg) skew(50deg);
}

.cn-wrapper li:nth-child(2) {
  -webkit-transform: rotate(30deg) skew(50deg);
  -ms-transform: rotate(30deg) skew(50deg);
  -moz-transform: rotate(30deg) skew(50deg);
  transform: rotate(30deg) skew(50deg);
}

.cn-wrapper li:nth-child(3) {
  -webkit-transform: rotate(70deg) skew(50deg);
  -ms-transform: rotate(70deg) skew(50deg);
  -moz-transform: rotate(70deg) skew(50deg);
  transform: rotate(70deg) skew(50deg);
}

.cn-wrapper li:nth-child(4) {
  -webkit-transform: rotate(110deg) skew(50deg);
  -ms-transform: rotate(110deg) skew(50deg);
  -moz-transform: rotate(110deg) skew(50deg);
  transform: rotate(110deg) skew(50deg);
}

.cn-wrapper li:nth-child(5) {
  -webkit-transform: rotate(150deg) skew(50deg);
  -ms-transform: rotate(150deg) skew(50deg);
  -moz-transform: rotate(150deg) skew(50deg);
  transform: rotate(150deg) skew(50deg);
}

.cn-wrapper li:nth-child(odd) a {
  background-color: #a11313;
  background-color: hsla(0, 88%, 63%, 1);
}

.cn-wrapper li:nth-child(even) a {
  background-color: #a61414;
  background-color: hsla(0, 88%, 65%, 1);
}

/* active style */
.cn-wrapper li.active a {
  background-color: #b31515;
  background-color: hsla(0, 88%, 70%, 1);
}

/* hover style */
.cn-wrapper li:not(.active) a:hover,
.cn-wrapper li:not(.active) a:active,
.cn-wrapper li:not(.active) a:focus {
  background-color: #b31515;
  background-color: hsla(0, 88%, 70%, 1);
}
.cn-wrapper li:not(.active) a:focus {
  position: fixed;
}
.opened-nav {
  border-radius: 50%;
  pointer-events: auto;
  width: 40em;
  height: 50em;
  margin-left: -20em;
  -webkit-transform: scale(1);
  -moz-transform: scale(1);
  -ms-transform: scale(1);
  transform: scale(1);
}
.cm-icon{
  display: inline-block;
  width:50px; 
  height:50px;
  transform: scale(0.7);
}
.icon-mainpage {
  background-image: url("../../imgs/icons8-document-50 (1).png");
}
.icon-calender{
    background-image: url("../../imgs/icons8-calendar-50.png");
}
.icon-settings {
    background-image: url("../../imgs/icons8-settings-50.png");
}
.icon-files{
    background-image: url("../../imgs/icons8-folder-50.png");
}
</style>
