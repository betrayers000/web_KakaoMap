<template>
    <div>
        <ProItem v-for="pro in proList" :key="pro.id" :pro="pro"/>
    </div>
</template>

<script>
import ProItem from "./ProItem"

export default {
    name: "ProList",
    components:{
        ProItem,
    },
    props:{
        proList: Array,
    },
    data:function(){
        return{

        }
    }

}
</script>

<style>

</style>