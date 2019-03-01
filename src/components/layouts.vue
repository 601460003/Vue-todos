<template>
  <section class="container"> <!--最外层容器-->
    <!--左边的容器-->
    <section class="menu">
      <ul v-for="food in foodList">
        <li><span class="count-list">{{food.count}}</span>{{food.name}}</li>
      </ul>
      <li>新增</li>
    </section>
    <!--右边的容器-->
    <section class="content-container">
      <div style="background: transparent;">
        <h1>Carol</h1>
        <input style="border: none;font-size: 16px;padding-left: 32px" type="text" placeholder="请输入">
      </div>
      <div style="    line-height: 55px;">
        <div v-for="food in foodList">
          <input type="checkbox" @click="onclick(food)" >
          <span v-if="food.checked">{{food.content}}</span>
          <span v-else ><s style="color: #999">{{food.content}}</s></span>
        </div>
        <!--<div  v-for="food in foodList">-->
        <!--<lable>-->
        <!--<input type="checkbox" name="checked" @click="onclick">-->
        <!--</lable>-->
        <!--<input class="input-a" type="text" placeholder="{{food.content}}" disabled="disabled" v-if="checked">-->
        <!--<s v-else style="color: #999">{{food.content}}</s>-->
        <!--</div>-->
      </div>
    </section>
  </section>


</template>
<script>

  export default {
    components: {},
    data() {
      return {

        count: 5,
        foodList: [
          {
            id: 1,
            name: 'Carol',
            checked: true,
            count: 5,
            content: '红局克造此问样外代斯段位般位报过,新有委条增入算具广务老部图装。'
          },
          {
            id: 2,
            name: 'Jessica',
            checked: true,
            count: 5,
            content: '品形系至关打国织度矿求须深教除感。出好战商与集级何议火越来。'
          },
          {
            id: 3,
            name: 'Sarah',
            checked: true,
            count: 5,
            content: '中专角除品难支以还火选学。满消派近件必术查率流面除总民信。'
          },
          {
            id: 4,
            name: 'Anthony',
            checked: true,
            count: 5,
            content: '路改术体报家以议备才果写复由矿。料个电酸他京往法会农部认王流历。'
          },
          {
            id: 5,
            name: 'Anna',
            checked: true,
            count: 5,
            content: '按做程装老位子制住金火按团上想况。局程快际使商其队五法问南地。'
          },
        ]
      }
    },
    methods: {
      onclick(food) {

        if (food.checked) {
          var list = this.foodList;
          for (var i = 0; i < list.length; i++) {
            if (food.id == list[i].id) {
              list[i].checked = false
              list[0].count = list[0].count - 1

            }
          }
        } else {
          var list = this.foodList
          for (var i = 0; i < list.length; i++) {
            if (food.id == list[i].id) {
              list[i].checked = true
              list[0].count = list[0].count + 1
            }
          }

          //   this.foodList  = this.foodList.map(e=>{
          //     if(e.id  == food.id)
          //       e.checked = true;
          //     return e;
          //   })
          // }


        }
      },
    }
  }
</script>


<style>
  body {
    background-color: #315481;
    background-image: linear-gradient(180deg, #315481, #918e82);
    background-repeat: no-repeat;
    background-attachment: fixed;
  }

  .container {
    width: 1200px;
    margin: 0 auto;
    text-align: center;
    color: #2c3e50;
  }

  .menu {
    width: 270px;
    height: 280px;
    float: left;
  }

  .menu ul {
    margin: 0;
    padding: 0;
  }

  .menu li {
    list-style-type: none;
    font-size: 16px;
    color: white;
    height: 40px;
    box-shadow: 0 1px 0 0 hsla(0, 0%, 100%, .15);
    padding-top: 15px;
    text-align: left;
    padding-left: 25px;
    line-height: 1.5em;
  }

  .count-list {
    transition: all .2s ease-in;
    background: hsla(0, 0%, 100%, .1);
    border-radius: 1em;
    float: right;
    font-size: .7rem;
    line-height: 1;
    margin-top: .25rem;
    margin-right: 1.5em;
    padding: .3em .5em;
    background: #2cc5d2;

  }

  /*右边*/
  .content-container {
    float: left;
    background: white;
    width: 900px;
    height: 920px;
    text-align: left;
    padding-left: 25px;
  }

  .input-a {
    font-size: 16px;
    width: 600px;
    border: none;
    background: transparent;
    padding-left: 8px;
  }

  .count-list-a {
    transition: all .2s ease-in;
    background: hsla(0, 0%, 100%, .1);
    border-radius: 1em;
    font-size: .7rem;
    line-height: 1;
    margin-top: .25rem;
    margin-right: 1.5em;
    padding: .3em .5em;
    background: #2cc5d2;
    color: white;
  }
</style>
