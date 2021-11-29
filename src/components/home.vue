<template>
<div>
<div class="avatar">
    <i-avatar :src="avatarUrl" size="large"></i-avatar>{{ nickName }}
</div>
<div class="grid">
<i-grid>
    <i-grid-item>
        <i-grid-icon>
            <i-icon type="time" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>历史</i-grid-label>
    </i-grid-item>
    <i-grid-item>
        <i-grid-icon>
            <i-icon type="collection" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>收藏</i-grid-label>
    </i-grid-item>
        <i-grid-item>
        <i-grid-icon>
            <i-icon type="setup" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>设置</i-grid-label>
    </i-grid-item>
</i-grid>
<i-grid>
    <i-grid-item>
        <i-grid-icon>
            <i-icon type="feedback" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>反馈</i-grid-label>
    </i-grid-item>
    <i-grid-item>
        <i-grid-icon>
            <i-icon type="message" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>通知</i-grid-label>
    </i-grid-item>
        <i-grid-item>
        <i-grid-icon>
            <i-icon type="more" size="32" color="#80848f" />
        </i-grid-icon>
        <i-grid-label>开发中</i-grid-label>
    </i-grid-item>
</i-grid>
</div>
</div>
</template>
<script>
export default {
  data () {
    return {
      nickName: '',
      avatarUrl: ''
    }
  },
  methods: {
    getUserIndex () {
      var that = this
      wx.getStorage({
        key: 'avatarUrl',
        success (res) {
          that.avatarUrl = res.data
        }
      })
      wx.getStorage({
        key: 'nickName',
        success (res) {
          that.nickName = res.data
        }
      })
    }
  },
  mounted () {
    this.getUserIndex()
  }
}
</script>
<style>
.avatar{
  position: absolute;
  margin-left: 50px;
  height: 1000px;
  top: 10%;
},
.grid{
  position: absolute;
  width: 100%;
  top: 30%;
}
</style>
