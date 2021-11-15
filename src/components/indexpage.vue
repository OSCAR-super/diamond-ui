<template>
<div>
<i-row>
    <i-col span="18" i-class="col-class">
        <i-panel title="圆角输入框">
          <i-input :value="value1" maxlength="100" type="number" mode="wrapped" placeholder="请输入搜索词" />
        </i-panel>
    </i-col>
    <i-col span="5" i-class="col-class">
      <i-button bind inline="true" class = "searching":click="handleClick" type="primary" shape="square" size="small">搜索</i-button>
    </i-col>
</i-row>
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
</style>