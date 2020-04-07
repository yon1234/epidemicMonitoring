<template>
  <div class="home">
    <headers></headers>
    <div class="conten">
      <div class="left">
        <show-num :nums="reportedData" :addNums="reportedDataAdd" :color="1" :typeNum="type[0]"></show-num>
        <show-num :nums="haartData" :addNums="haartDataAdd" :color="2" :typeNum="type[1]"></show-num>
        <pie-chart></pie-chart>
      </div>
      <div class="centre">
        <map-chart></map-chart>
        <line-chart></line-chart>
      </div>
      <div class="right">
        <show-num :nums="contactData" :addNums="contactDataAdd" :color="3" :typeNum="type[2]"></show-num>
        <show-num :nums="HealthData" :addNums="HealthDataAdd" :color="4" :typeNum="type[3]"></show-num>
        <bar-chart></bar-chart>
      </div>
    </div>
  </div>
</template>
<script>
//引入子组件
import Headers from "./header";
import ShowNum from "./showNum";
import PieChart from "./pieChart";
import MapChart from "./mapchart";
import LineChart from "./lineChart";
import BarChart from "./barChart";
export default {
  props: {},
  data() {
    return {
      // 此处数据需后台动态获取
      reportedData: 2321,
      reportedDataAdd: 231,
      haartData: 2321,
      haartDataAdd: 121,
      contactData: 1221,
      contactDataAdd: 231,
      HealthData: 2322,
      HealthDataAdd: 253,
      type: ["上报数", "发热数", "接触数", "健康数"]
    };
  },
  computed: {},
  created() {},
  mounted() {},
  watch: {},
  methods: {},
  components: {
    Headers,
    ShowNum,
    PieChart,
    MapChart,
    LineChart,
    BarChart
  }
};
</script>

<style scoped >
.home {
  background-color: #09173d;
}
.conten {
  display: flex;
  height: 650px;
}
.left {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px 0;
  align-items: center;
}
.centre {
  flex: 2;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px 0;
  align-items: center;
}
.right {
  flex: 1;
  display: flex;
  flex-direction: column;
  padding: 20px 0;
  justify-content: space-between;
  align-items: center;
}
</style>
