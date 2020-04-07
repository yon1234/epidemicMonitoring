<template>
  <div id="pie"></div>
</template>
<script>
export default {
  props: [],
  data() {
    return {
      option: {
        title: {
          text: "健康状况占比",
          subtext: "",
          left: "left",
          padding: [10, 10, 10, 10],
          textStyle: {
            fontSize: 16,
            color: "#c4d3ed"
          }
        },
        tooltip: {
          trigger: "item",
          show: true,
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        },
        series: [
          {
            name: "",
            type: "pie",
            radius: "55%",
            center: ["50%", "60%"],
            data: [
              { value: 20, name: "发热" },
              { value: 40, name: "健康" },
              { value: 30, name: "咳嗽" },
              { value: 10, name: "其他" }
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)"
              }
            }
          }
        ]
      }
    };
  },
  computed: {},
  created() {},
  mounted() {
    this.getPieChart();
    this.pppp()
  },
  watch: {},
  methods: {
    getPieChart() {
      var myChart = this.$echarts.init(document.getElementById("pie"));
      myChart.resize =window.onresize 
      myChart.setOption(this.option);
      console.log(this);
      
    },

    pppp:()=>console.log(this)},
  components: {}
};
</script>
<style scoped >
#pie {
  width: 70%;
  height: 250px;
  box-shadow: 0px 1px 4px 1px rgb(63, 125, 233);
}
</style>
