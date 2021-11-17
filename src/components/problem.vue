<template>
<div>
<div class = "button" v-if="start == '1'">
  <i-button @click="handleClick" type="primary" size="large">开始问题搜索</i-button>
</div>
<div class = "button1" v-if="start == '2'">
  <i-button type="ghost" size="small">你要找的是开源帖子</i-button>
</div>
<div class = "yes" v-if="start == '2'">
  <i-button @click="handleClick" type="primary" >是</i-button>
  <i-button @click="handleClick" type="primary" >否</i-button>
</div>
<div class = "clear" v-if="start == '2'">
  <i-button inline="true" @click="handleClick1" type="primary" >清空</i-button>
</div>
</div>
</template>
<script>
export default {
  data () {
    return {
      start: '1',
      answer: []
    }
  },
  methods: {
    handleClick () {
      this.start = '2'
    },
    handleClick1 () {
      this.start = '1'
    }
  }
}
</script>
<style>
.button{
  position:absolute;
  width:100%;
  top:38%;
}
.button1{
  position:absolute;
  width:100%;
  top:20%;
},
.yes{
  position:absolute;
  width:300px;
  top:50%;
  margin-left: 38px;  
},
.clear{
  position:absolute;
  margin-left: 275px;
}
</style>