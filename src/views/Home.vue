<template>
  <v-layout class="home d-flex">
    <v-col cols=6>
      <h1>pro List</h1>
      <ProList/>
    </v-col>
    <v-col cols=6>
      <h1>Map</h1>
      <KakaoMap :markers="markers"/>
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
      markers : [
        {lat:33.450701 , lng: 126.570667},
        {lat:33.550720 , lng: 126.570690},
        {lat:33.650770 , lng: 126.570567},
      ]
    }
  },
  components: {
    ProList,
    KakaoMap

  }
}
</script>
