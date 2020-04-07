<template>
  <div id="map"></div>
</template>
<script>
import xiaogan from "../../static/json/xgdatas.json"; //引入孝感市地理地图坐标
export default {
  props: {},
  data() {
    return {
      option: {
        title: {
          text: "",
          subtext: "",
          x: "left"
        },
        tooltip: {
          trigger: "item",
          formatter: "{b}",
          itemSize: "14px"
        },
        legend: {
          orient: "vertical",
          x: "center",
          data: [""]
        },
        dataRange: {
          x: "left",
          y: "bottom",

          splitList: [
            { start: 0, end: 0 },
            { start: 1, end: 9 },
            { start: 10, end: 99 },
            { start: 100, end: 499 },
            { start: 500, end: 999 }
          ],
          color: ["#c25331", "#c3742d", "#beae3c", "#2080c7"],
          textStyle: {
            color: "#fff"
          }
        },
        series: [
          {
            name: "孝感市",
            type: "map",
            mapType: "xiaogan",
            roam: false,
            itemStyle: {
              normal: {
                label: {
                  show: true,
                  textStyle: {
                    color: "#ffff"
                  }
                }
              },
              emphasis: { label: { show: true } }
            },
            data: [] //后台传过来的数据
          }
        ]
      }
    };
  },
  computed: {},
  created() {},
  mounted() {
    this.creatMap();
  },
  watch: {},
  methods: {
    async creatMap() {
      // 模拟请求后台数
      let res = await this.axios.get("../../static/json/data.json");
      this.option.series[0].data = res.data.mapData;
      let myChart = this.$echarts.init(document.getElementById("map"));
      this.$echarts.registerMap("xiaogan", xiaogan);
      window.onresize = myChart.resize;
      myChart.setOption(this.option);
    }
  },
  components: {}
};
</script>

<style scoped >
#map {
  width: 100%;
  height: 400px;
}
</style>
