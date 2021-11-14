<template>
<div>
  <div v-if="current == 'mine'">
    <home></home>
  </div>
<i-tab-bar class="flex" :current="current" color="#f759ab" @change="handleChange">
    <i-tab-bar-item key="homepage" icon="homepage" current-icon="homepage_fill" title="首页"></i-tab-bar-item>
    <i-tab-bar-item key="group" icon="group" current-icon="group_fill" title="朋友"></i-tab-bar-item>
    <i-tab-bar-item key="remind" icon="remind" current-icon="remind_fill" title="通知"></i-tab-bar-item>
    <i-tab-bar-item key="mine" icon="mine" current-icon="mine_fill" title="我的"></i-tab-bar-item>
</i-tab-bar>
</div>
</template>
<script>
import home from '@/components/home'

export default {
  data () {
    return {
      current: 'homepage'
    }
  },
  components: {
    home
  },
  methods: {
    handleChange (detail) {
      this.current = detail.mp.detail.key
    }
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
