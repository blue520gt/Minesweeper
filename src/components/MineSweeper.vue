<template>
  <!-- 最外层，包括难度选项、关闭、重启、倒计时 -->
  <div class="wholePage">
    <!-- 包含所有小方格的大格子 -->
    <div class="bigDiamond">
      <!-- 将statusNow的内容画在界面上  两个v-for  -->
      <!-- 遍历30列，并通过i记录遍历到了第几个 -->
      <div v-for="(mineSweeperWidthItem,i) in statusNow" class="columnOfDiamond">
        <!-- 遍历16行，并通过j记录遍历到了第几个 -->
        <div
          v-for="(mineSweeperHeightItem,j) in mineSweeperWidthItem"
          class="littleDiamond"
          v-on:click="clickBoom(i,j)"
        ></div>
      </div>
    </div>
  </div>
</template>



<script>
// mineSweeperStatus:
// status = 1: 没有点击鼠标&没有鼠标悬浮
// status = 2: 鼠标悬浮
// status = 3: 左键点击&击中雷
// status = 4: 左键点击 & 未击中雷 & 周围有0个雷
// status = 5: 左键点击 & 未击中雷 & 周围有1个雷
// status = 6: 左键点击 & 未击中雷 & 周围有2个雷
// status = 7: 左键点击 & 未击中雷 & 周围有3个雷
// status = 8: 左键点击 & 未击中雷 & 周围有4个雷
// status = 9: 左键点击 & 未击中雷 & 周围有5个雷
// status = 10: 左键点击 & 未击中雷 & 周围有6个雷
// status = 11: 左键点击 & 未击中雷 & 周围有7个雷
// status = 12: 左键点击 & 未击中雷 & 周围有8个雷
// status = 13: 右键点击（n * 3 + 1）次（小红旗）
// status = 14: 右键点击（n * 3 + 2）次（问号）
export default {
  name: "MineSweeper",
  data() {
    return {
      statusNow: [],
      mineSweeperWidth: 30,
      mineSweeperHeight: 16
    };
  },
  created() {
    for (var i = 0; i < this.mineSweeperWidth; i++) {
      this.statusNow[i] = [];
      for (var j = 0; j < this.mineSweeperHeight; j++) {
        this.statusNow[i][j] = 0;
      }
    }
  },
  methods: {
    clickBoom: function(i, j) {
      //   点击后修改model的值,onclick事件+子控件和父控件的交互
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.littleDiamond {
  width: 16px;
  height: 16px;
  position: relative;
  top: 10px;
  left: 10px;
  font-family: "黑体";
  font-size: 40px;
  font-weight: bold;
  line-height: 100px;
  float: left;
  margin-right: 0px;
  margin-bottom: 0px;
  color: white;
}
.bigDiamond {
  width: 16px;
  height: 16px;
  /* position: relative; */
  /* top: 0px;
  left: 0px;
  /* font-family: "黑体";
  font-size: 40px;
  font-weight: bold;
  line-height: 100px;
  float: left;
  margin-right: 10px;
  margin-bottom: 10px; */
  color: darkgray;
}
.wholePage {
  width: 550px;
  height: 300px;
  background-color: grey;
}
</style>
