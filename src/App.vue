<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <!--<li><router-link  to="/HelloWorld" >商品</router-link></li>-->

    <router-view/>
    <!--<props mess="组件的引入跟操作"></props>-->
    <!--<demo></demo>-->
    <!--<wo></wo>-->
  </div>
</template>

<script>
import  demo from './components/demo'
import  props from './components/props'
import  wo from './components/wo'
export default {
  name: 'App',
  components:{
         demo,props,wo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
