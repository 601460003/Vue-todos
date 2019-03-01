<template>
<div class="wo">
  <form  @submit="addUser">
    <input type="text" v-model="newUser.name">
    <input type="text"  v-model="newUser.email">
    <input type="submit" value="subit">
  </form>

  <ul>

    <li v-for="li in list">
      <input type="checkbox" v-model="li.contacteds" class="too">
      <span :class='{contacted:li.contacteds}'>
        {{li.name}}:{{li.email}}
      </span>
      <button @click="deleteUse(li)">×</button>

    </li>

  </ul>
</div>
</template>

<script>
    export default {
        name: "wo",

      data(){
          return{
            newUser:{},
            list:[
              {
                name:'zhangzhiwei',
                email:'zhangzhiwei@qq.com',
                contacteds:false
              },
              {
                name:'zhangzhiwei',
                email:'zhangzhiwei@qq.com',
                contacteds:false
              },
              {
                name:'zhangzhiwei',
                email:'zhangzhiwei@qq.com',
                contacteds:false
              },
            ]
          }
      },
      methods:{
        addUser(){
     var car={name:this.newUser.name, email:this.newUser.email, contacted:false}
          this.list.push(car)
          this.newUser.name=this.newUser.email='';
        },
        deleteUse(li){
         this.list.splice(this.list.indexOf(li),1);
        },
      },
    }
</script>

<style scoped>
.contacted{
  color: red;
  text-decoration: line-through;
}
</style>
