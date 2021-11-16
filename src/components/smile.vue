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
            value="starIndex4">
            starIndex4星
        </i-rate>
    </i-cell>
</i-cell-group>
</div>
</template>
export default {
  data () {
    return {
      starIndex4 : 4
    }
  },
  onChange1(e){
        const index = e.detail.index;
        this.setData({
            'starIndex1' : index
        })
    },
    onChange2(e){
        const index = e.detail.index;
        this.setData({
            'starIndex2' : index
        })
    },
    onChange3(e){
        const index = e.detail.index;
        this.setData({
            'starIndex3' : index
        })
    },
    onChange5(e){
        const index = e.detail.index;
        this.setData({
            'onChange5' : index
        })
    }
});
<style>
.avatar1{
  text-align: center;
}
</style>