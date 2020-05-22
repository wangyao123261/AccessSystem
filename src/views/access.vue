<template>
<div>
<department id="department" :name="name">
</department>
<visitor id="visitor">
</visitor>
</div>
</template>
<script>
import visitor from "./visitor/index.vue"
import department from "./department/index.vue"
export default {
name:"Access",
components: {
    //调用组件
    visitor,
    department
},
data(){
return{
name:''
}
},
method:{

}
}
</script>
<style>
#department{
margin-top:40px;
width:70%;
margin-left:50px
}
#visitor{
    width:20%;
    position:absolute;
    right:130px;
    top:50px
}
</style>
