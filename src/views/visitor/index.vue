<template>
<div>
<div style="background:blue;padding-top:10px;padding-bottom:10px;text-align:center;">访客信息</div>
<table>
 <thead>
 <tr>
  <th width="120">访客姓名</th>
  <th width="120">被访对象</th>
  <th >被访对象部门</th>
 </tr>
 </thead>
<!-- <tbody>
    <draggable v-model="tableData"  tag="tr" v-for="(item,id) in tableData" :key="id" @end='end'
:options="{group:{name:'visitor',put:false,pull:'clone'},sort:false}" handle = ".singlePerson">
    <td class="singlePerson">{{item.name}} </td>
  <td class="item-drag">{{item.interviewee}}</td>
  <td class="item-drag">{{item.department}}</td>
</draggable>
 </tbody> -->
     <draggable v-model="tableData"  tag="tbody"  @end='end'
:options="{group:{name:'visitor',put:false,pull:'clone'},sort:false}"  handle = ".singlePerson">
<tr v-for="(item,id) in tableData" :key="id">
    <td class="singlePerson">{{item.name}} </td>
  <td class="item-drag">{{item.interviewee}}</td>
  <td class="item-drag">{{item.department}}</td>
</tr>
</draggable>
</table>
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
    console.log(ev)
    // $emit('add',ev)
  }
}
}
</script>
<style>
td{
  text-align:center;
}
table, td, th{
  border:1px solid grey;
}
table{
  border-collapse:collapse;
 width:100%}
</style>
