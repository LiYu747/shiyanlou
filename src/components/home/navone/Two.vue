<template>
  <div>
    <div class="box2 flex al-center pos-rel">
      <div class="m-box flex al-center">
        <div class="mar">
          <img src="./img/logo.png" alt />
        </div>
        <div>全部课程</div>
      </div>

      <div class="flex al-center">
        <div class="text m-l2">路径</div>
        <div class="text m-l3">训练营</div>
        <div class="text m-l3">楼+</div>
        <div class="text m-l3">会员</div>
        <div class="jay">
          <div class="flex text">
            <div class="m-l3">社区</div>
            <div style="font-size: 14px;margin-left: 3px;">▼</div>
          </div>
          <div class="none-box">
            <div class="aaa m-t3">讨论</div>
            <div class="aaa n-text">教程库</div>
            <div class="aaa n-text">直播</div>
            <div class="aaa">比赛</div>
          </div>
        </div>
        <div class="pos-abs" style="  right: 30px;">
          <input
            type="text"
            placeholder="  搜索 课程/问题"
            class="mag"
            style=" width: 250px;height: 40px;"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  props: {},
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
.box2 {
  width: 1200px;
  height: 60px;
  background: white;
}
.m-box {
  width: 300px;
  height: 60px;
  background: rgb(8, 191, 145);
  color: white;
}
.mar {
  margin-top: 5px;
  margin-left: 10px;
}

.mag {
  border: 1px solid rgb(206, 212, 218);
  border-radius: 5px;
}
.mag:focus {
  outline: none;
  border: 1px solid rgb(101, 215, 186);
}
.mag:hover {
  border: 1px solid rgb(101, 215, 186);
}
.text:hover {
  color: rgb(101, 215, 186);
}
.none-box {
  width: 160px;
  height: 280px;
  display: none;
  position: absolute;
  left: 550px;
  border-radius: 5px;
  font-size: 18px;
  background: white;
}
.jay:hover {
  .none-box {
    display: block;
  }
}

.aaa {
  width: 130px;
  height: 60px;
  padding-left: 20px;
  display: flex;
  align-items: center;
}
.aaa:hover {
  background: rgb(247, 247, 247);
  color: rgb(8, 191, 145);
  display: flex;
  align-items: center;
}
</style>