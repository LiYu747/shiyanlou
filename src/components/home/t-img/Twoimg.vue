<template>
 <div class="tem-box pos-rel flex ju-center">
     <Tigson :msg='msg'></Tigson> 
    <LUNb>  </LUNb>
   

    
      
      
 </div>
</template>

<script>
import axios from "axios";
import Tigson from '../t-img/t-son/Tigson'
import LUNb from '../t-img/t-son/LUNb'

 export default {
   name: '',
   props: {

   },
   components: {
       Tigson,
       LUNb,
      
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