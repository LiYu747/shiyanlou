<template>
 <div class="who swiper-container">
    <swiper ref="mySwiper" :options="swiperOptions">
    <swiper-slide v-for="(item,index) in ptes" :key="index">
      <div class="ato" :style="{background:item.background_color }">
           <img :src="item.picture_url" alt="" class="p-img">
        </div> 
    </swiper-slide>
    
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
      <div class="swiper-button-prev"></div><!--左箭头。如果放置在swiper-container外面，需要自定义样式。-->
    <div class="swiper-button-next"></div><!--右箭头。如果放置在swiper-container外面，需要自定义样式。-->
 </div>
</template>

<script>
import axios from "axios";
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
 export default {
   name: '',
   props: {
   },
   components: {
         Swiper,
    SwiperSlide
   },
   data () {
     return {
        ptes: [],
        swiperOptions: {
        pagination: {
          el: ".swiper-pagination"
        },
        // Some Swiper option/callback...
        autoplay:true,
          navigation: {
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    },
      },
      
    

     }
   },
   methods: {
          getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/banner-pictures`)
        .then(res => {
          // console.log(res.data);
          this.ptes = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    }
   },
   mounted() {
       this.getData();
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
.who{
    width: 200000px;
    position: relative;
    
}
.p-img{
    position: relative;
    left: 220px;
}
.swiper-container{
    --swiper-theme-color: #ff6600;/* 设置Swiper风格 */
    --swiper-navigation-color: #00ff33;/* 单独设置按钮颜色 */
    --swiper-navigation-size: 30px;/* 设置按钮大小 */
}
.swiper-button-prev{
    left: 550px;
}
.swiper-button-next{
    right: 60px ;
}
</style>