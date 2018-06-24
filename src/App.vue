<template>
  <div id="app">
    <div id='nav'>
      <router-link to="/"> Home </router-link>
      <router-link to="about"> About </router-link>
    </div>
    <transition name="anim" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  @import 'htpps://cdn.jsdelivr.net/npm/animate.css@3.5.1'

  body {
    background: rgb(233,233,233);
    font-family: Arial,Helvetica, sans-serif;
  }

  html, body {
    height: calc(100% - 50px);
  }

  #app {
    background: #fff;
    width: 50%;
    padding: 30px;
    border-radius: 10px;
    margin: 50px auto 0 auto;
    height: calc(60% - 50px);
  }

  .page {
    width: inherit;
  }

  .anim-enter-active {
    opacity: 0;
    animation: coming 1s .5s;
  }

  .anim-leave-active {
    animation: going 1s;
  }

  @keyframes going {
    from {
      transform: translateX(0);
    }

    to {
      transform: translateX(-50px);
      opacity: 0;
    }
  }

  @keyframes coming {
    from {
      transform: translateX(-50px);
      opacity: 0;
    }

    to {
      transform: translateX(0px);
      opacity: 1;
    }
  }

</style>
