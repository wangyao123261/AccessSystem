<template>
<div>
<div class='top'>访客信息</div>
<table>
 <thead>
 <tr>
  <th width="30%">访客姓名</th>
  <th width="30%">被访对象</th>
  <th >被访对象部门</th>
 </tr>
 </thead>
     <draggable v-model="tableData"  tag="tbody"   @end="end"
:options="{group:{name:'visitor',put:false,pull:'clone'},sort:false}"  handle = ".singlePerson">
<tr v-for="(item,id) in tableData" :key="id">
    <td class="singlePerson">{{item.name}} </td>
  <td >{{item.interviewee}}</td>
  <td >{{item.department}}</td>
</tr>
</draggable>
</table>
<!-- <div class="name" >
  <div class="one">访客姓名</div>
   <draggable v-model="tableData"    @end="end"
:options="{group:{name:'visitor',put:false,pull:'clone'},sort:false}"  >
<li v-for="(item,id) in tableData" v-bind:key="id" class="li"> {{item.name}}</li>
 </draggable>
</div>
<div class="duixiang" >
  <div class="one">被访对象</div>
  <li v-for="(item,id) in tableData" v-bind:key="id" class="li"> {{item.interviewee}}</li>
  </div>
<div  class="bumen">
  <div class="one">被访对象部门</div>
  <li v-for="(item,id) in tableData" v-bind:key="id" class="li"> {{item.department}}</li></div> -->

</div>
</template>
<script>
import draggable from "vuedraggable";
export default {
name:"Visitor",
components: {
    //调用组件
    draggable,
},
props: {

tableData:{
type:Array,
//required: true,
default: function () {
        return  [
        {name: '张三',
        interviewee:'马化腾',
        department:'市场部',},
        {name: '李四',
        interviewee:'马化腾',
        department:'市场部',},
         {name: '王五',
          interviewee:'马化腾',
           department:'市场部'},
           {name: '张三',
           interviewee:'马化腾',
          department:'市场部',},
        ]
      }
},
},
data(){
return{

}
},
methods:{
  end(ev){
    console.log(ev.to.innerHTML)
    console.log(ev)
    // $emit('add',ev)
  },

}
}
</script>
<style>
td{
  text-align:center;
  padding:10px 0px
}
th{
  padding:10px 0px;

}
table, td, th{
  border:1px solid grey;
}
table{
  border-collapse:collapse;
 width:100%}
 .top{
   background:#36a3f7;;padding-top:10px;padding-bottom:10px;text-align:center;
 }
 /* .name{
   width:30%;float:left;
   border:1px solid grey;

 }
 .duixiang{
   width:30%;float:left;
   border-top:1px solid grey;
   border-bottom:1px solid grey;

 }
 .bumen{
   width:40%;
  float:left;
   border:1px solid grey;

 }
 .li{
padding:0;text-align:center;padding:15px 0px;
border-top:1px solid grey;

 }
 .li:first-child {
    margin-top: 0px;
}
.one{
  font-weight:bold;
  padding:10px 0px;
  text-align:center
} */
</style>
