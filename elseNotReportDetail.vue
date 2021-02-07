<template>
  <div class="report-dom">
    <div class="report-not-header">
      <p>今日未上报公司</p>
      <div @click="isActive=!isActive">+</div>
    </div>
    <collapse-transition>
      <div class="collapse-wrap report-not-content" v-show="isActive">
        <table>
            <tr class="theader-title">
              <td>地区</td>
              <td>确诊</td>
              <td>疑似</td>
              <td>医学观察</td>
              <td>死亡</td>
              <td>操作</td>
            </tr>
            <tr>
              <td>xxx公司</td>
              <td :style="{color:colorArr[1]}"><span>5</span>(+1,-2)</td>
              <td :style="{color:colorArr[2]}"><span>5</span>(+1,-2)</td>
              <td :style="{color:colorArr[3]}"><span>5</span>(+1,-2)</td>
              <td :style="{color:colorArr[4]}"><span>5</span>(+1,-2)</td>
            </tr>
             <tr>
              <td>xxx公司</td>
              <td><span>5</span>(+1,-2)</td>
              <td><span>5</span>(+1,-2)</td>
              <td><span>5</span>(+1,-2)</td>
              <td><span>5</span>(+1,-2)</td>
            </tr>
        </table>
      </div>
    </collapse-transition>
  </div>
</template>

<script>
import collapseTransition from '../../libs/translation'
export default {
  data() {
    return {
      isActive: true,
      colorArr:['#cdd4ff','#fd4e5f','#ffb83d',"#67aff7",'#6c6c6c']
    }
  },
  components: {
    collapseTransition
  }
}
</script>

<style lang="less" scoped>
.report-not-header{
  display: flex;
  padding: .2rem;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid #eee;
}
.report-dom{
  font-size: .5rem;
  border: 1px solid #ddd;
  width: 95%;
  margin: .3rem auto;
}
.report-not-content{
  width: 100%;
  font-size: .4rem;
  table{
    width: 100%;
    text-align: center;
    vertical-align: middle;
    tr{
      width: 100%;
      border-bottom: 1px solid #ddd;
      td{
        padding: .2rem 0;
      }
    }
    tr:nth-child(2n){
      background: #f2f2f2
    }
  }
}
.theader-title{
  td:nth-child(1){
    background: #cdd4ff;
  }
  td:nth-child(2){
    background: #ffd0ce;
  }
  td:nth-child(3){
    background: #ffe0a0;
  }
  td:nth-child(4){
    background: #b9d9ff;
  }
  td:nth-child(5){
    background: #e2e2e2;
  }
  td:nth-child(6){
    background: #c6f1dd;
  }
  td:not(last-child){
      border-right: 1px solid #fff;
  }
}
</style>