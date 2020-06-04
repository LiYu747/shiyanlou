<template>
 <div class="box flex ju-center">
        <div class="center">
           <div class="flex one-box al-center pos-rel">
             <div class="text">楼+&nbsp;&nbsp;实战课程</div>  
               <div class="vae"></div>
               <div class="tt">定期开班，导师助教全程辅导，最快优先成长</div>
               <div class=" pos-abs rig tt">更多></div>
               </div>

               <div class="t-box flex ju-between">
                  <div  v-for="(item,index) in arr.slice(0,4)" :key="index">
                        <div class="aa"> <img :src="item.picture_url" alt="" class="p-img">
                        <div class="im-box">
                           <div class=" fz-18 title">{{item.title}}</div> 
                           <div class="open">最近班次：{{item.open_time}}</div> 
                        </div>
                        </div> 
                  </div>
               </div>
        </div>
 </div>
</template>

<script>
import axios from 'axios'
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
      arr:[]
     }
   },
   methods: {
      getData(){
         axios.get(`http://120.78.14.107/api/v2/index/louplus`).then((res)=>{
                        // console.log(res.data)
                      this.arr = res.data
         }).catch((err)=>{
                console,log(err)
         })
      }
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
.box{
    width: 100%;
}
.center{
    width: 1200px;
    height: 310px;
  
}
.one-box{
    width: 100%;
    height: 100px;
    
   
}
.text{
    font-size: 24px;
    color: rgb(86,86,86);
}
.rig{
    right: 0;
}
.vae{
    width: 2px;
    height: 20px;
    background: rgb(86,86,122);
    margin: 0 15px;
}
.aa:hover{
    box-shadow: 3px 3px 3px 3px #eee;
}
.t-box{
    width: 100%;
    height: 200px;
}
.p-img{
    width: 280px;
    border-radius: 10px 10px 0 0;
}
.im-box{
    width: 280px;
    height: 100px;
    background: white;
  
}
.title{
    margin-top: -5px;
    padding: 16px 10px;
    color: rgb(86,86,86);
}
.open{
    padding-left: 10px;
    color: rgb(164,173,196);
}
.tt{
    color: rgb(102,102,126);
}

</style>