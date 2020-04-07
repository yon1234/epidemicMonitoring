<template>
  <div id="lineChart"></div>
</template>
<script>
export default {
  props: [],
  data() {
    return {
      option: {
        title: {
          text: "居民上报统计",
          left: "left",
          padding: [10, 10, 10, 10],

          textStyle: {
            fontSize: 16,
            color: "#c4d3ed"
          }
        },
        tooltip: {
          trigger: "axis"
        },
        legend: {
          left: "right",
          textStyle: {
            fontSize: 12,
            color: "#c4d3ed"
          },
          padding: [10, 10, 10, 10],

          data: []
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },
        toolbox: {
          feature: {
            saveAsImage: {}
          }
        },
        xAxis: {
          type: "category",
          boundaryGap: false,
          axisLabel: {
            formatter: "{value}",
            textStyle: {
              color: "#fff"
            }
          },

          data: []
        },
        yAxis: {
          type: "value",
          axisLabel: {
            formatter: "{value}",
            textStyle: {
              color: "#fff"
            }
          }
        },
        series: []
      }
    };
  },
  computed: {},
  created() {},
  mounted() {
    this.getLineChart();
  },
  watch: {},
  methods: {
    async getLineChart() {
      // 模拟请求后台数
      let res = await this.axios.get("../../static/json/data.json");
      this.option.legend.data = res.data.linedata.legenddata;
      this.option.xAxis.data = res.data.linedata.xAxisdata;
      this.option.series = res.data.linedata.yAxisdata;
      var myChart = this.$echarts.init(document.getElementById("lineChart"));
     
      myChart.setOption(this.option);
    }
  },
  components: {}
};
</script>

<style scoped >
#lineChart {
  width: 100%;
  height: 200px;
  box-shadow: 0px 1px 4px 1px rgb(63, 125, 233);
}
</style>
