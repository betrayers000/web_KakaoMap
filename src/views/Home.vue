<template>
  <v-layout class="home d-flex">
    <v-col cols=6>
      <h1>pro List</h1>
      <ProList :proList="proList"/>
    </v-col>
    <v-col cols=6>
      <h1>Map</h1>
      <KakaoMap :markers="proList"/>
    </v-col>
  </v-layout>
</template>

<script>
import ProList from "../components/ProList"
import KakaoMap from "../components/KakaoMap"

export default {
  name: 'home',
  data: ()=>{
    return{
      proList : [
        {id: 1, title: "안녕하세요", content:"2000원", lat:33.450701 , lng: 126.570667},
        {id: 2, title: "하이", content:"3000원", lat:33.550720 , lng: 126.570690},
        {id:3, title: "어서오세요", content:"4000원", lat:33.650770 , lng: 126.570567},
      ]
    }
  },
  components: {
    ProList,
    KakaoMap

  }
}
</script>
