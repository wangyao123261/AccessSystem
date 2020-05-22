<template>
<div>
<div style="width:120px;height:500px;display:inline-block;margin-left:30px;text-align:center;border:1px solid grey;border-radius:10px 10px 0px 0px;" 
v-for="item in department" v-bind:key="item.id">
<div style="background:blue;color:white;padding-top:10px;padding-bottom:10px;border-radius:10px 10px 0px 0px">{{item.name}}</div>
<el-input v-model="input" style="height:10px"></el-input>
<slot></slot>

</div>
</div>
</template>
<script>
import draggable from "vuedraggable";
export default {
name:"Department",
components: {
    //调用组件
    draggable,
},
props: {

department:{
type:Array,
default: function () {
        return  [
        {id:1,name: '总经办大门',people:
          [
            {id:1,name: '蒲xx'},
            {id:2,name: '李xx'},
            {id:3,name: '王XX'},
            {id:4,name: '廖xx'},
            {id:5,name: '涂XX'},
          ]},
        {id:2,name: '算法部大门',people:
          [
            {id:1,name: '蒲xx'},
            {id:2,name: '李xx'},
            {id:3,name: '王XX'},
            {id:4,name: '廖xx'},
            {id:5,name: '涂XX'},
          ]},
        {id:3,name: '开发部大门',people:
          [
            {id:1,name: '蒲xx'},
            {id:2,name: '李xx'},
            {id:3,name: '王XX'},
            {id:4,name: '廖xx'},
            {id:5,name: '涂XX'},
          ]},
        {id:4,name: '产品部大门',people:
          [
            {id:1,name: '蒲xx'},
            {id:2,name: '李xx'},
            {id:3,name: '王XX'},
            {id:4,name: '廖xx'},
            {id:5,name: '涂XX'},
          ]},
        {id:5,name: '设计部大门',people:
          [
            {id:1,name: '蒲xx'},
            {id:2,name: '李xx'},
            {id:3,name: '王XX'},
            {id:4,name: '廖xx'},
            {id:5,name: '涂XX'},
          ]},
        ]
      }
},


},
data(){
return{
input: ''
}
}
}
</script>
<style>

li{
padding: 8px 25px;
text-align:left;
list-style-type: none;
/* font-size: ; */
}
li:first-child{
  margin-top:20px
}
</style>
