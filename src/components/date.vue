<template>
<div class="block-date">
  <div class="block">
  <span class="demonstration">周</span>
  <el-date-picker
    v-model="value3"
    type="week"
    format="yyyy 第 WW 周"
    placeholder="选择周">
  </el-date-picker>
</div>
<div class="block">
  <span class="demonstration">月</span>
  <el-date-picker
    v-model="value4"
    @change="mounth1"
    type="month"
    placeholder="选择月">
  </el-date-picker>
</div>
<div class="block dd-block">
  <span class="demonstration">日</span>
  <el-date-picker
  popper-class="icon-date"
    v-model="value5"
    align="right"
    type="date"
    format="dd"
    @change="ddDate"
    placeholder="选择日">
  </el-date-picker>
</div>
</div>
</template>

<script>
let moment = require('moment')
export default {
  data () {
    return {
      value3: '',
      value4: '',
      value5: ''
    }
  },
  methods: {
    mounth1 (val) {
      this.value5 = val
    },
    ddDate (val) {
      console.log(moment(val).format('DD'))
    }
  }
}
</script>
<style spcoed>
.block-date{
  display: flex;
  align-items: center;
}
.icon-date .el-date-picker__header{
     display: none;
   }
  .icon-date .prev-month,.icon-date .next-month{
    pointer-events: none;
   }
</style>
