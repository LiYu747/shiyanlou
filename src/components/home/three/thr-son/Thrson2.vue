<template>
  <div class="box">
    <div class="one-box flex al-center pos-rel" v-for="(item,index) in txt.slice(0,1)" :key="index">
      <div class="text">{{item.classify_name}}</div>
      <div class="vae"></div>
      <div class="tt">{{item.description}}</div>
      <div class="pos-abs rig tt">更多></div>
    </div>

    <div class="t-box">
      <div class="flex flex-w ju-between" v-for="(item,index) in txt.slice(0,1)" :key="index">
        <img :src="item.recommend_course.picture_url" alt class="r-img bttom" />
        <div class="aa" v-for="(item1,index1) in item.courses" :key="item1.id">
          <img :src="item1.picture_url" alt class="p-img" />
          <div class="i-box bttom pos-rel">
              <div class="no-box pos-rel">
                   <div class="m-tt m-l1">{{item1.name}}</div>
            <div class="fz-12 mm m-l1">{{item1.description}}</div>
              </div>
         
             <div class="stude pos-abs fz-12 flex al-center">{{item1.students_count}}
                 <div class="en" v-if="index1>1&&index1<5"></div>
             </div>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "",
  props: {},
  components: {},
  data() {
    return {
      txt: []
    };
  },
  methods: {
    getData() {
      axios
        .get(`http://120.78.14.107/api/v2/index/classfication-courses`)
        .then(res => {
          console.log(res.data);
          this.txt = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    }
  },
  mounted() {
    this.getData();
  },
  watch: {},
  computed: {}
};
</script>

<style scoped lang='scss'>
.box {
  width: 1200px;
  height: 600px;
  background: yellowgreen;
}
.one-box {
  width: 1200px;
  height: 100px;
}
.text {
  font-size: 24px;
  color: rgb(86, 86, 86);
}
.vae {
  width: 2px;
  height: 20px;
  background: rgb(86, 86, 122);
  margin: 0 15px;
}
.rig {
  right: 0;
}
.tt {
  color: rgb(102, 102, 126);
}

.t-box {
  width: 100%;
  height: 400px;
  background: sandybrown;
}
.p-img {
  width: 280px;
  height: 170px;
}
.r-img {
  width: 600px;
  height: 280px;
}
.i-box {
  width: 280px;
  height: 110px;
  background: wheat;
  margin-top: -5px;
  color: rgb(102,102,127);
}
.bttom {
  margin-bottom: 20px;
}
.stude {
  width: 280px;
  height: 60px;
  background: white;
  top:65px ;
  padding-left: 20px;
}
.no-box {
  width: 280px;
  height: 85px;
  background: white;
  top: 0px;
  white-space: wrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.aa:hover{
    .no-box{
        height: 130px;
        position: relative;
        top: -60px;
        transform: translate();
        transition: all 0.5s;
    }
}
.m-tt{
    margin-top: 22px;
}
.mm{
    margin-top: 20px;
}
.en{
    width: 60px;
    height: 30px;
    background: red;
}
</style>