<template>
<div>
<div class="avatar">
    <i-avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large"></i-avatar>名字
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
