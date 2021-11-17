<template>
<div>
<div class="avatar1">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
<div class="avatar2">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
<div class="avatar2">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>
</div>
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
      starIndex: 4
    }
  }
}
</script>
<style>
.avatar1{
  text-align: center;
}
</style>