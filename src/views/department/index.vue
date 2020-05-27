<template>
<div>
  <div v-for="item in department" v-bind:key="item.id" style="width:120px;height:auto;display:inline-block;margin-left:30px;">
    <el-button style="width:34px;padding:3px;position:relative;left:77px" @click="del" v-if="checkbox">删除</el-button>
<div style="height:500px;overflow:auto;border:1px solid grey;border-radius:10px 10px 0px 0px;position:relative" 
>

<div style="background:#36a3f7;text-align:center;color:white;padding-top:10px;padding-bottom:10px;border-radius:10px 10px 0px 0px">{{item.name}}</div>
<el-input v-model="item.input" style="width:85%;float:left">
<el-button slot="append" icon="el-icon-search" style="padding:0px"></el-button>
</el-input>
<i class="el-icon-edit-outline" @click="cancel"></i>
  <draggable v-model="item.people"  
   v-bind="{group:{name:'visitor',put:true,pull:false},sort:false,disabled:false}" >

   <li v-for="people in item.people" v-bind:key="people.id"><el-checkbox  v-if="item.checkbox"> </el-checkbox>&nbsp;&nbsp;{{people.name}}</li>
      </draggable>
</div>
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
input: '',
// checkbox:false,
checked:false,
input:[]
}
},
  created: function () {
    this.department.map(val=>{val.input;val.checkbox})
    console.log(this.department)
  },
methods:{
  add(ev){
    console.log(ev)
  },
  cancel(){
    if(this.checkbox==false){this.checkbox=true}
    else{
      this.checkbox=false
    }
  },
  del(){

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
  margin-top:40px
}
#department /deep/ input {
height:22px;
padding:0px;

}
#department /deep/ .el-input-group__append {
width:20px;
padding:0px;

}
#department /deep/ button {
margin:0px

}
.el-icon-edit-outline{
float:left;
width:15%;
padding:3px 0px
}
</style>
