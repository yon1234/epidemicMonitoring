<template>
  <div class="barChart">
    <div>健康状态较好的前五</div>
    <ul>
         <!-- //此处需后台数据动态v-for生成 -->
      <li>
        <p>园林办事处</p>
        <el-progress :stroke-width="5" :percentage="75"></el-progress>
      </li>
      <li>
        <p>园林办事处</p>
        <el-progress :stroke-width="5" :percentage="75"></el-progress>
      </li>
      <li>
        <p>园林办事处</p>
        <el-progress :stroke-width="5" :percentage="75"></el-progress>
      </li>
      <li>
        <p>园林办事处</p>
        <el-progress :stroke-width="5" :percentage="75"></el-progress>
      </li>
        <li>
        <p>园林办事处</p>
        <el-progress :stroke-width="5" :percentage="75"></el-progress>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {};
  },
  computed: {},
  created() {},
  mounted() {},
  watch: {},
  methods: {},
  components: {}
};
</script>
<style scoped >
.barChart {
  width: 70%;
  box-shadow: 0px 1px 4px 1px rgb(63, 125, 233);
  padding: 10px 20px;
  box-sizing: border-box;
  color: #c4d3ed;
}

.barChart ul li {
  padding: 10px;
  font-size: 12px;
}
</style>
