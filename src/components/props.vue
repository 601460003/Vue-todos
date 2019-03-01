<template>
    <div>
      <h1>{{title}}</h1>
      <button @click="NB('利用NB来传参想要的东西')">欢迎来到英雄联</button>
      <input type="text" v-on:keyup="DD" v-on:keyup.enter="CC">
      <p >{{mess}}</p>
    </div>
</template>

<script>
    export default {
        name: "props",
      data(){
          return{
            title:'你好，世界',
          }
      },
      props:{
          mess:{
            default:'就是大SB'
          }
      },
        methods:{
          NB(NB) {
            alert(NB)
          },
          DD () {
            console.log('plae.....')
          },
          CC () {
            alert('你的输入有误 ')
          }
        }
    }
</script>

<style scoped>
div{
  color: red;
}
</style>
