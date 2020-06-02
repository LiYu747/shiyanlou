<template>
  <div class="center pos-rel">
    <div class="box">
      <div class="mar-t2 aa flex al-center pos-rel" v-for="(item,index) in msg" :key="index">
        <div class="jack m-l2">
          <div>{{item.name}}</div>
        </div>

        <div class="jack m-l2">{{item.tags[0].name}}</div>

        <div class="jack m-l2">{{item.tags[1].name}}</div>

        <div class="line"></div>
      </div>

         <div class="none-box">
           <div class=""  v-for="(item,index) in msg" :key="index">
             <div class="baa flex-w">
             <div class="m-l2 m-t2">{{item.name}}</div>
             
             <div v-for="(item1,index1) in item.tags" :key="index1">
                   
                     <div class=" m-l2">{{item1.name}} </div>  
             </div>
   </div>
           </div>
         </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {
    msg: {
      type: Array
    }
  },
  components: {},
  data() {
    return {};
  },
  methods: {},
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.center {
  width: 1200px;
}
.box {
  width: 300px;
  height: 650px;
  background: chartreuse;
  position: absolute;
  left: 0;
  color: white;
}
.no-box {
  width: 500px;
  height: 500px;
  background: red;
}
.line {
  width: 270px;
  height: 1px;
  background: violet;
  margin-left: 15px;
  position: absolute;
  bottom: -2px;
}
.jack:hover {
  color: violet;
}
.mar-t2 {
  height: 70px;
  width: 300px;
}
.mar-t2:hover {
  color: rgb(102, 102, 102);
  background: white;
}
.none-box {
  width: 370px;
  height: 380px;
 
 position: absolute;
  left: 300px;
  top: 0px;

  // display: none;
}
.aa:hover {
  .none-box {
    display: block;
  }
}
.baa{
  width: 370px;
  height: 150px;
  display: flex;
  background: orangered;

}
</style>