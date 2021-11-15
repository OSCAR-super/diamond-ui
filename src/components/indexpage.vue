<template>
<div>
<i-panel title="圆角输入框">
    <i-input :value="value1" type="number" mode="wrapped" placeholder="请输入搜索词" />
</i-panel>
<div class = "searching">
  <i-button bind class = "searching":click="handleClick" type="primary" shape="circle" size="small">搜索</i-button>
</div>
<i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
    <view slot="content">内容不错</view>
    <view slot="footer">尾部内容</view>
</i-card>
<i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
    <view slot="content">内容不错</view>
    <view slot="footer">尾部内容</view>
</i-card>
</div>
</template>
<script>
export default {
  data () {
    return {
      value1: ''
    }
  }
}
</script>
<style>
.searching{
  width:150px;
  text-align: center;
}
</style>