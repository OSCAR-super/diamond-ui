<template>
<div>
<div v-for="count in 3">
  <i-card title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
      <view slot="content">内容不错</view>
      <view slot="footer">尾部内容</view>
  </i-card>
</div>
<div>
<i-page :current="current" total="5" @change="pageChange">
    <view slot="prev">
        <i-icon type="return"></i-icon>
        上一页
    </view>
    <view slot="next">
        下一页
        <i-icon type="enter"></i-icon>
    </view>
</i-page>
</div>
</div>
</template>
export default {
  data () {
    return {
      value1: '',
      current: 1
    }
  },
  methods: {
    pageChange (detail) {
      if (detail.mp.detail.type === 'next' && this.current !== 5) {
        this.current++
      } else if (detail.mp.detail.type === 'prev' && this.current !== 1) {
        this.current--
      }
    }
  }
}
</script>