<template>
  <div class="wraper">
    <div class="page-title">迭代质量总结</div>

    <div class="tabs-wraper">
      <el-tabs v-model='activeName' @tab-click='handleClick'>
        <el-tab-pane label='横向对比' name='first'>
          <div class="chart" ref="chartRef">
            echarts
          </div>
        </el-tab-pane>
        <el-tab-pane label='当前迭代数据' name='second'>当前迭代数据</el-tab-pane>
        <el-tab-pane label='线上严重及以上问题列表' name='third'>线上严重及以上问题列表</el-tab-pane>
        <el-tab-pane label='未关闭缺陷列表' name='fourth'>未关闭缺陷列表</el-tab-pane>
        <el-tab-pane label=' 典型 bug' name='fifve'> 典型 bug</el-tab-pane>
      </el-tabs>
    </div>

  </div>
</template>

<script>
import * as echarts from "echarts";

export default {
  name: 'demo-page',
  data() {
    return {
      activeName: 'first'
    }
  },
  mounted() {
    this.initChart()
  },
  methods: {
    initChart() {
      let chartInstance = echarts.getInstanceByDom(this.$refs.chartRef);
      if (chartInstance == null) {
        chartInstance = echarts.init(this.$refs.chartRef);
      }

      const option = {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: [150, 230, 224, 218, 135, 147, 260],
            type: 'line'
          }
        ]
      };

      chartInstance.setOption(option)

    },

    handleClick(tab, event) {
      console.log(tab, event);
    }
  }
}

</script>

<style scoped>
.wraper {
  padding: 16px;
}

.page-title {
  padding: 8px;
  margin-bottom: 4px;
  background-color: #fff;
  font-weight: bold;
  font-size: 18px;
}

.tabs-wraper {
  padding: 8px;
  margin-bottom: 4px;
  background-color: #fff;
  background-color: #fff;
}

.chart {
  width: 500px;
  height: 500px;
}
</style>