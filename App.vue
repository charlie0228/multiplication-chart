<template>
  <div class="container">
    <div class="grid_wrapper">
      <div class="title_area">
        <span class="text_c">九九乘法表 </span>
        <span>MULTIPLICATION CHART</span>
        <div class="point tl">x</div>
        <div class="point tr">x</div>
        <div class="point bl">x</div>
        <div class="point br">x</div>
      </div>
      <div class="area" v-for="num in 8" :key="num">
        <div class="large-num">{{ num + 1 }}</div>
        <div class="num" v-for="second_num in 9" :key="second_num">
          {{ num + 1 }} x {{ second_num }} = {{ (num + 1) * second_num }}
        </div>
      </div>
    </div>
    <footer class="footer">
      Copyright © 2019 AzureBlue. All rights reserved.
    </footer>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Noto+Sans+TC:500|Open+Sans:400,700');
  body {
    font-family: 'Open+Sans', sans-serif;
    font-size: 24px;
    color: #2EB738;
  }
  .text_c {
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 56px;
  }
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 1280px;
    margin: 0 auto;
  }
  .grid_wrapper {
    display: grid;
    padding: 80px 85px;
    background: #F0F0F0;
    grid-template-columns: 350px 350px 350px;
    grid-column-gap: 30px;
    grid-template-rows: 366px 366px 366px;
    grid-row-gap: 40px;
  }
  .title_area {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    &:before {
      content: '';
      border-bottom: 1px solid #2EB738;
      position: absolute;
      width: 80%;
      left: 10%;
      bottom: 0;
    }
    &:after {
      content: '';
      border-top: 1px solid #2EB738;
      position: absolute;
      width: 80%;
      left: 10%;
      top: 0;
    }
    .point {
      position: absolute;
      height: 0px;
      &.tl {
        top: -16px;
        left: -5px;
      }
      &.tr {
        top: -16px;
        left: 344px;
      }
      &.bl {
        top: 349px;
        left: -5px;
      }
      &.br {
        top: 349px;
        left: 344px;
      }
    }
  }
  .area {
    background: #FFFFFF;
    box-shadow: 0px 3px 10px #D8D8D8;
    border-radius: 100px 0px 30px 0px;
    padding: 64px 40px;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  .large-num {
    font-size: 128px;
    font-weight: 700;
    text-shadow: 4px 3px #F0F0F0;
    text-align: center;
    line-height: 0.8;
    padding-bottom: 12px;
    margin-right: 50px;
  }
  .num {
    margin: -1px 50px 5px 0px;
  }
  .footer {
    height: 34px;
    background: #2EB738;
    text-align: right;
    font-size: 16px;
    color: #F0F0F0;
    line-height: 2.2;
    padding-right: 85px;
  }
</style>
