<template>
    <div id="map" style="width:500px;height:400px;">
    </div>
</template>

<script>
const kakao = window.daum.maps

export default {
    name : "KakaoMap",
    data: function(){
        return {
            mapInfo : []
        }
    },
    props:{
        markers :{
            type: Array,
            default: null
        }
    },
    methods :{
        loadMap(markers){
            var container = document.getElementById('map')
            console.log(`container: ${container}`)
            var options = {
                center: new kakao.LatLng(33.450701, 126.570667),
                level: 3
            };
            var map = new kakao.Map(container, options)
            var info = []

            //map click event
            kakao.event.addListener(map, 'click', function(e){
                console.log(e)
                console.log(info)
                if (info.length != 0){
                    info.forEach(wd=>{
                        wd.close()
                    })
                    info = []
                }
            })
            // create marker
            if (markers != null){
                markers.forEach(function(marker){
                    var markerPosition = new kakao.LatLng(marker.lat, marker.lng)
                    var nMarker = new kakao.Marker({
                        position : markerPosition,
                        clickable : true,
                    })
                    nMarker.setMap(map)
                    var iwContent = '<div style="padding:5px;">Hello World!</div>', // 인포윈도우에 표출될 내용으로 HTML 문자열이나 document element가 가능합니다
                    iwRemoveable = true; // removeable 속성을 ture 로 설정하면 인포윈도우를 닫을 수 있는 x버튼이 표시됩니다
                    // 인포윈도우를 생성합니다
                    var infowindow = new kakao.InfoWindow({
                        content : iwContent,
                        removable : iwRemoveable
                    });
                    // 마커에 클릭이벤트를 등록합니다
                    kakao.event.addListener(nMarker, 'click', function() {
                        // 마커 위에 인포윈도우를 표시합니다
                        console.log(this.mapInfo)
                        if (info.length != 0){
                            info[0].close()
                            info = []
                        }
                        info.push(infowindow)
                        info[0].open(map, nMarker);
                        this.mapInfo = info 
                    });
                })
            }
            else {
                console.log(map)
            }
        },
    },
    mounted(){
        this.loadMap(this.markers)
    }
}
</script>

<style>

</style>