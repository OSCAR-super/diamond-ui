<template>
<div>
<div class="avatar1">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
<div class="avatar2">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
<div class="avatar3">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
<i-row class="sign">
  <div @click="activity">
    <i-icon type="activity" size="60" color="#80848f" />签到
  </div>
<i-modal title="签到成功" :visible="visible" :actions="actions" :action-mode="vertical" @click="handleClose"></i-modal>
</i-row>
<i-cell-group>
<i-cell title="禁用点击和手势选择星">
        <i-rate 
            disabled="true"
            :value="starIndex">
            xx年xx月xx日
        </i-rate>
    </i-cell>
</i-cell-group>
</div>
</template>
<script>
export default {
  data () {
    return {
      visible: false,
      starIndex: 4,
      actions: [
        {
          name: '确定',
          color: '#ff9900'
        }
      ]
    }
  },
  methods: {
    activity () {
      this.visible = true
    },
    handleClose () {
      this.visible = false
    }
  }
}
</script>
<style>
.avatar1{
  text-align: center;
},
.sign{
  text-align: center;
}
</style>