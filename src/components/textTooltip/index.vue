<template>
  <div>
    <el-tooltip :effect="effect" :content="text" :placement="placement" :disabled="disableTip">
      <div class="ellipsis" @mouseover="onMouseOver" :style="{color:color}">
        <span ref="ellipsis" :style="{color,fontSize,fontWeight}">{{ text }}</span>
      </div>
    </el-tooltip>
  </div>
</template>

<script>
export default {
  props:{
    text:{
      type: String,
      default:''
    },
    placement: {
      type: String,
      default:'top'
    },
    color: String,
    fontSize: {
      type: String,
      default: '14px'
    },
    fontWeight: {
      type: [String, Number],
      default: 'normal'
    },
    effect: { 
      type: String, 
      default: 'dark' 
    },
  },
  data() {
    return {
      disableTip: false
    }
  },
  created() {

  },
  mouted() {

  },
  methods: {
    onMouseOver() {
      // 获取元素父级可视宽度
       const parentWidth = this.$refs['ellipsis'].parentNode.offsetWidth
       // 获取元素可视宽度:设置了元素不换行，就可以知道元素的实际宽度
       const contentWidth = this.$refs['ellipsis'].offsetWidth

       this.disableTip = contentWidth <= parentWidth
    }
  },
}
</script>
<style scoped lang='scss'>
.ellipsis {
 width: 100%;
 overflow: hidden;
 white-space: nowrap;
 text-overflow: ellipsis;
}
</style>