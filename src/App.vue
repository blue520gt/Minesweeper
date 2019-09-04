<template>
  <div id="app">
    <img src="./assets/minesweeper.png" width="150px" height="150px" />
    <p align="left">1.判断出不是雷的方块上按下左键，可以打开该方块。</p>
    <p align="left">2.如果方块上出现数字，则该数字表示其周围3×3区域中的地雷数（一般为8个格子，对于边块为5个格子，对于角块为3个格子。所以扫雷中最大的数字为8）；</p>
    <p align="left">3.如果方块上为空（相当于0），则可以递归地打开与空相邻的方块；如果不幸触雷，则游戏结束。</p>
    <p align="left">4.在判断为地雷的方块上按下右键，可以标记地雷（显示为小红旗），重复一次或两次操作可取消标记。</p>

    <router-view />
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
