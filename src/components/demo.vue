<template>
  <div class="demo">
    <h1>用户</h1>

    <!--添加用户信息-->
    <form v-on:submit="addUser">
      <input type="text" v-model="newUser.name" placeholder="Enter name">
      <input type="text" v-model="newUser.email" placeholder="Enter email">
      <input type="submit" value="Submit">
    </form>

    <!--展示用户信息-->


    <ul>
      <li v-for="list in items" style="padding: 10px;list-style-type: none">
        <input type="checkbox" class="toggle" v-model="list.contacted">

        <span :class="{coutacted:list.contacted}">
         {{list.name}}:{{list.email}}
    <button v-on:click="deleteUser(list)">×</button>
    </span>

      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "demo",
    data() {
      return {
        newUser: {},
        items: [
          {
            name: 'zhangzhiwei',
            email: 'zhangzhiwei@qq.com',
            contacted: false,
            id:1
          },
          {
            name: 'haunghuahau',
            email: 'haunghuahau@qq.com',
            contacted: false,
            id:2
          },
          {
            name: 'lixiaolong',
            email: 'lixiaolong@qq.com',
            contacted: false,
            id:3
          }
        ]
      }
    },
    methods: {
      addUser: function (e) {   //增加的方法
        // console.log('hellow');
        this.items.push({
          name: this.newUser.name,
          email: this.newUser.email,
          contacted: false
        });
        e.preventDefault();
      },
      deleteUser: function (list) {     //s删除的方法
        this.items.splice(this.items.indexOf(list), 1)
      }
    }
  }
</script>

<style scoped>
  .coutacted {
    text-decoration: line-through;
    color: red;
  }
</style>
