<template>
<div>
  <i-modal title="您未登录！" :visible="visible" :actions="actions" :action-mode="vertical"><i-button  @click
  ="bindGetUserInfo" type="primary">获取权限</i-button></i-modal>
  <div v-if="current == 'remind'">
    <smile></smile>
  </div>
  <div v-if="current == 'homepage'">
    <indexpage></indexpage>
  </div>
  <div v-if="current == 'mine'">
    <home></home>
  </div>
  <div v-if="current == 'group'">
    <problem></problem>
  </div>
<i-tab-bar class="flex" :current="current" color="#f759ab" @change="handleChange">
    <i-tab-bar-item key="homepage" icon="browse" current-icon="browse_fill" title="发现"></i-tab-bar-item>
    <i-tab-bar-item key="group" icon="search" current-icon="searchfill" title="问题搜索"></i-tab-bar-item>
    <i-tab-bar-item key="remind" icon="emoji" current-icon="emoji_fill" title="每日一笑"></i-tab-bar-item>
    <i-tab-bar-item key="mine" icon="mine" current-icon="mine_fill" title="我的"></i-tab-bar-item>
</i-tab-bar>
</div>
</template>
<script>
import home from '@/components/home'
import indexpage from '@/components/indexpage'
import smile from '@/components/smile'
import problem from '@/components/problem'
export default {
  data () {
    return {
      current: 'homepage',
      visible: false,
      actions: [{}],
      userInfo: {}
    }
  },
  components: {
    home,
    indexpage,
    smile,
    problem
  },
  methods: {
    bindGetUserInfo () {
      var userProfile
      var that = this
      wx.getUserProfile({
        desc: '用于获取自己的头像',
        success (res) {
          userProfile = res.userInfo
          if (userProfile) {
            that.userInfo = userProfile
            wx.setStorage({
              key: 'nickName',
              data: that.userInfo.nickName
            })
            wx.setStorage({
              key: 'avatarUrl',
              data: that.userInfo.avatarUrl
            })
            wx.login({
              success (res) {
                console.log(res.code)
                wx.request({
                  url: 'http://389f80y058.zicp.vip/cou/auth/userWxLogin',
                  data: {
                    code: res.code
                  },
                  method: 'POST',
                  header: {
                    'content-type': 'application/json'
                  },
                  success: (res) => {
                    console.log(res.data.data.token)
                    wx.setStorage({
                      key: 'token',
                      data: res.data.data.token
                    })
                  }
                })
              },
              fail: (res) => {
                console.log('LOGIN失败', res)
              }
            })
            that.visible = false
          }
        }
      })
    },
    verifyToken () {
      var that = this
      wx.getStorage({
        key: 'token',
        success (res) {
          console.log(res.data)
          that.visible = true
        },
        fail () {
          that.visible = true
        }
      })
    },
    handleChange (detail) {
      this.current = detail.mp.detail.key
    }
  },
  mounted () {
    this.verifyToken()
  }
}
</script>

<style>
.flex{
  position:absolute;
  width:100%;
  top:90%;
}
</style>
