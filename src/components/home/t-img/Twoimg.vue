<template>
 <div class="tem-box flex-d al-center">
      <Tigson :msg='msg'></Tigson>
      <Tigimg></Tigimg>
 </div>
</template>

<script>
import axios from "axios";
import Tigson from '../t-img/t-son/Tigson'
import Tigimg from '../t-img/t-son/Tigimg'
 export default {
   name: '',
   props: {

   },
   components: {
       Tigson,
       Tigimg
   },
   data () {
     return {
       msg : []
     }
   },
   methods: {
           getData() {
      axios
        .get(
          `http://120.78.14.107/api/v2/index/categories`
        )
        .then(res => {
         console.log(res.data)
          this.msg = res.data;
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
.tem-box{
  width: 100%;
  
}
</style>