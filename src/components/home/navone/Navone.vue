<template>
 <div class="box1 flex al-center pos-rel">
       <div><img src="https://static.shiyanlou.com/frontend/dist/img/9f43b00.svg" alt="实验楼" class="img" data-v-7629dae3=""></div>
       <div>做实验，学编程</div>
       <div class="right flex pos-abs al-center">
         <div class="hov">企业版</div>
         <div class="vae"></div>
         <div class="hov">学校版</div>
         <div class="text">登录</div>
         <div class="back flex al-center ju-center">注册</div>
       </div>

 </div>
</template>

<script>
 export default {
   name: '',
   props: {
   },
   components: {

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
  .box1{
    width: 1200px;
    height: 100px;
    font-size: 18px;
  }
  .right{
    right: 0;
    font-size: 18px;
    color: rgb(153,153,153);
  }
  .vae{
    width: 1px;
    height: 20px;
    background: rgb(153,153,153);
    margin: 0 10px;
  }
  .back{
    width: 100px;
    height: 50px;
    background: rgb(8,191,145);
    color: white;
  }
  .text{
    margin: 0 30px;
    color: rgb(8,191,145);
  }
  .text:hover{
    color: rgb(153,153,153);
  }
  .img{
    width: 150px;
    height: 150px;
  }
  .hov:hover{
    color: rgb(8,191,145);
  }
</style>
