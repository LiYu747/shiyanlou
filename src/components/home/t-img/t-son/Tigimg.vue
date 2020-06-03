<template>
 <div class="ti-box flex ju-center">
        <div v-for="item in img" :key="item.id">
                 <img :src="item.picture_url" alt="">
        </div>
 </div>
</template>

<script>
import axios from "axios";
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
       img:[]
     }
   },
   methods: {
          getData() {
      axios
        .get(
          `http://120.78.14.107/api/v2/index/banner-pictures`
        )
        .then(res => {
         console.log(res.data)
          this.img = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    },
   },
   mounted() {
    this.getData()
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
.ti-box{
    width: 100%;
    height: 700px;
    background: salmon;
}
</style>