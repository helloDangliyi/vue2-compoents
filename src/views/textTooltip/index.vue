<template>
  <div class="bg">
    <div class="main">
      父盒子
      <textTooltip text="内容自嘎内容"></textTooltip>
    </div>
  </div>
</template>

<script>
import textTooltip from '@/components/textTooltip'
export default {
  components:{textTooltip},
  data() {
    return {

    }
  },
  created() {

  },
  mouted() {

  },
  methods: {

  },
}
</script>
<style scoped lang='scss'>
.bg{
  padding: 20px;
  .main{
    width: 150px;
    height: 350px;
    background-color: olive;
  }
}

</style>