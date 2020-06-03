<template>
  <div class="center pos-rel">
    <div class="box  flex-d al-center">
      <div class="mar-t2 aa flex al-center pos-rel" v-for="(item,index) in msg" :key="index">
        <div class="jack m-l2">
          <div>{{item.name}}</div>
        </div>

        <div class="jack m-l2">{{item.tags[0].name}}</div>

        <div class="jack m-l2">{{item.tags[1].name}}</div>

        <div class="line"></div>

        <div class="none-box" :style="{ top: index > 3 ? ((-57 * (index-4))-70)+'px' : '0px' }">
          <div class="baa">
            <div class="pdd">{{item.name}}</div>
            <div class="flex flex-w m-t3 fz-12">
              <div v-for="(item1,index1) in item.tags" :key="index1">
                <div class="flex al-center m-t1">
                  <div class="vae"></div>
                  {{item1.name}}
                </div>
              </div>
            </div>
            <div class="text">课程推荐</div>
            <div v-for="item2 in item.recommend_courses" :key="item2.id">
              <div class="m-l2 fz-12 m-b2">{{item2.name}}</div>
            </div>
          </div>
        </div>
      </div>
      <div class="flex ju-center al-center m-t2 jnj fz-14">经营专区</div>
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
  background:   rgba(225,225,225,0.3);
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
  background: rgb(188,188,188);
  margin-left: 15px;
  position: absolute;
  bottom: -2px;
}
.jack:hover {
  color: rgb(8,191,145);
}
.mar-t2 {
  height: 70px;
  width: 300px;
}
.mar-t2:hover {
  color: rgb(102, 102, 102);
  background: white;
}
.jnj:hover{
   color: rgb(102, 102, 102);
  background: white;
}
.none-box {
  width: 370px;
  height: 380px;
  position: absolute;
  left: 300px;
  top: 0px;
  display: none;
}
.aa:hover {
  .none-box {
    display: block;
  }
}

.baa {
  width: 370px;
  height: 400px;
  background: white;
}
.pdd {
  width: 120px;
  background: rgb(238, 238, 238);
  position: relative;
  top: 20px;
  left: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.vae {
  width: 1px;
  height: 15px;
  background: black;
  margin: 0 20px;
}
.text {
  width: 120px;
  background: rgb(238, 238, 238);
  margin: 20px 20px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.jnj{
  border: 1px solid rgb(231,210,145);
  width: 100px;
  height: 30px;
  border-radius: 30px;
}
</style>