<template>
  <div>
    <div class="report-not">
      <div class="report-not-header">
        <p>今日未上报公司</p>
        <div @click="isActive=!isActive">+</div>
      </div>
      <collapse-transition>
        <div class="collapse-wrap report-not-content" v-show="isActive">
          <p class="gailan">
            <span>12</span>/
            <span>60</span>
          </p>
          <div class="">1232,12323,23131,123123,123,123</div>
        </div>
      </collapse-transition>
    </div>
  </div>
</template>

<script>
import collapseTransition from '../../libs/translation'
export default {
  data() {
    return {
      isActive: true
    }
  },
  components: {
    collapseTransition
  }
}
</script>

<style lang="less" scoped>
.report-not {
  font-size: 0.5rem;
  border: 1px solid #ddd;
  width: 95%;
  margin: 0 auto;
}
.report-not-header{
  display: flex;
  padding: .2rem;
  align-items: center;
  justify-content: space-between;
  
}
.report-not-content{
  border-top: 1px solid #ddd;
  padding:.3rem;
  word-break: break-all;
}
.gailan{
  margin-bottom: .2rem;
}
</style>