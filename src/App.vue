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
    font-family: Arial,Helvetica, sans-serif;
  }

  html, body {
    height: calc(100% - 50px);
    background: slateblue;
  }

  #app {
    width: 50%;
    padding: 30px;
    border-radius: 10px;
    margin: 50px auto 0 auto;
    height: calc(60% - 50px);
  }

  #nav a {
    color: whitesmoke;
    font-weight: bolder;
    margin: 0 .2rem;
  }
  #nav a:hover {
    cursor: pointer;
    color: lightblue;
  }

  .page {
    width: 100%;
    padding: 1rem;
    background: #fff;
    margin-top: .6rem;
    box-shadow: 0 0 20px darkslateblue;
  }

  .anim-enter-active {
    opacity: 0;
    animation: entering 1s .5s;
  }

  .anim-leave-active {
    animation: leaving 1s;
  }

  @keyframes leaving {
    from {
      transform: translateX(0);
    }

    to {
      transform: translateX(-50px);
      opacity: 0;
    }
  }

  @keyframes entering {
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
