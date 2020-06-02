<template>
 <div class="box flex-d al-center">
   
         <Navone></Navone>
         <Two></Two>
         <Twoimg></Twoimg>
 </div>
</template>

<script>
import Navone from '../components/home/navone/Navone'
import Two from '../components/home/navone/Two'
import Twoimg from '../components/home/t-img/Twoimg'


 export default {
   name: '',
   props: {
   },
   components: {
        Navone,
        Two,
        Twoimg
   },
   data () {
     return {

     }
   },
   methods: {

   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
   .box{
     width: 100%;
     height: 160px;
     background: rgb(249,249,249);
     cursor: pointer;
   }
</style>