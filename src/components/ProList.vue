<template>
    <div>
        <ProItem v-for="pro in proList" :key="pro" :pro="pro"/>
    </div>
</template>

<script>
import ProItem from "./ProItem"

export default {
    name: "ProList",
    components:{
        ProItem,
    },
    data:function(){
        return{
            proList : [1,2,3,4,5,6]
        }
    }

}
</script>

<style>

</style>