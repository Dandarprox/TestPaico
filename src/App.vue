<template>
  <div id="app">
    <div class="layout">
    <div class="title" ref="title">COMGRA</div>
    <div class="main-content">
      <router-view></router-view>
    </div>

    <div class="menu">
      <menu-component></menu-component>
    </div>
  </div>
  </div>
</template>

<script>
import MenuComponent from './components/Menu.vue';
import {TweenLite, Power2, Elastic, TimelineLite} from "gsap/TweenMax";

export default {
  components: {
    MenuComponent
  },
  mounted() {
    let title = this.$refs.title;

    TweenLite
      .from(title, 1, {
        left: '-100px',
        opacity: 0
      });
  }
}
</script>

<style type="text/css">
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}
::-webkit-scrollbar-button {
  width: 0px;
  height: 0px;
}
::-webkit-scrollbar-thumb {
  background: #e1e1e1;
  border: 0px none #ffffff;
  border-radius: 50px;
}
::-webkit-scrollbar-thumb:hover {
  background: #ffffff;
}
::-webkit-scrollbar-thumb:active {
  background: #f3784d;
}
::-webkit-scrollbar-track {
  background: #666666;
  border: 0px none #ffffff;
  border-radius: 50px;
}
::-webkit-scrollbar-track:hover {
  background: #666666;
}
::-webkit-scrollbar-track:active {
  background: #333333;
}
::-webkit-scrollbar-corner {
  background: transparent;
}
</style>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+HK:700&display=swap');

html, body {
  margin: 0;
  padding: 0;
  font-family: 'Noto Sans HK', sans-serif;
}

* {
  box-sizing: border-box;
}

.layout {
  display: flex;
  overflow: hidden;
}

.main-content {
  width: calc(100vw - 90px);
  height: 100vh;
  overflow: auto;
}

.menu {
  flex: 0 1;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.spacer {
  width: 100vw;
  height: 200vh;
}

.title {
  font-size: 42px;
  color: $color-orange;
  position: fixed;
  top: 5%;
  left: 5%;
  font-weight: bold;
  z-index: 3;
}

</style>
