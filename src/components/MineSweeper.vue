<template>
  <!-- 最外层，包括难度选项、关闭、重启、倒计时 -->
  <div class="wholePage">
    <!-- 操作按钮区域 -->
    <div class="optionOfDegree">
      <b>选项</b>
    </div>
    <!-- 包含所有小方格的大格子 -->
    <div class="bigDiamond">
      <!-- 将statusNow的内容画在界面上  两个v-for  -->
      <!-- 遍历16行，并通过i记录遍历到了第几个 -->
      <div v-for="(mineSweeperWidthItem,i) in statusNow" class="columnOfDiamond">
        <!-- 遍历30列，并通过j记录遍历到了第几个 -->
        <button
          v-for="(mineSweeperHeightItem,j) in mineSweeperWidthItem"
          class="littleDiamond"
          v-on:click="clickBoom(i,j)"
        ></button>
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
      mineSweeperWidth: 16,
      mineSweeperHeight: 30
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
/* 最外的div */
.wholePage {
  width: 550px;
  height: 361px;
  margin: 0 auto;
  background-color: white;
  border-radius: 5px;
  border: 2px solid black;
  box-shadow: 8px 8px 30px 5px gray;
}
/* 难度选项 */
.optionOfDegree {
  width: 530px;
  height: 30px;
  background-color: rgb(192, 192, 192);
  position: relative;
  top: 10px;
  left: 10px;
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: left;
  border-radius: 5px;
}
/* 包含所有小格子的大div */
.bigDiamond {
  width: 530px;
  height: 291px;
  background-color: rgb(192, 192, 192);
  position: relative;
  top: 10px;
  left: 10px;
  border-radius: 5px;
  /* margin-right: 1px; */
  /* margin-bottom: 1px; */
}
/* 所有行的样式 */
.columnOfDiamond {
  width: 510px;
  height: 16px;
  background-color: white;
  position: relative;
  top: 10px;
  left: 10px;
  /* margin-right: 1px; */
  margin-bottom: 1px;
}
/* 所有列的样式 */
.littleDiamond {
  width: 16px;
  height: 16px;
  position: relative;
  display: inline-block;
  /* float: left; */
  /* top: 10px;
  left: 10px; */
  margin-right: 1px;
  margin-bottom: 1px;
  /* margin: auto, auto; */
  background-color: rgb(192, 192, 192);
  cursor: pointer;
}
.littleDiamond:hover {
  width: 16px;
  height: 16px;
  position: relative;
  display: inline-block;
  /* float: left; */
  /* top: 10px;
  left: 10px; */
  /* margin-right: 1px; */
  margin-bottom: 1px;
  /* margin: auto, auto; */
  background-color: blue;
  cursor: pointer;
}
</style>
