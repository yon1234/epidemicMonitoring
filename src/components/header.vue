<template>
  <div class="header">
    <div class="time">
      <span>{{time}}</span>
    </div>
    <div class="title">
      <h3>孝感市新型冠状病毒肺炎疫情监控系统</h3>
    </div>
    <div class="login">
      <div class="user">
        <span class="el-icon-s-custom"></span>
        <el-dropdown>
          <el-button size="mini">
            卫建委
            <i class="el-icon-arrow-down el-icon--right"></i>
          </el-button>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>卫建委</el-dropdown-item>
            <el-dropdown-item>卫建委</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </div>
      <div class="nav">
        <el-button size="mini">疫情监控</el-button>
        <el-button size="mini">居民上报</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      gettime: "",
      time: ""
    };
  },
  computed: {},
  created() {
    this.currentTime();
   
  },
  mounted() {},
  watch: {},
  methods: {
    getTime() {
      var _this = this;
      let yy = new Date().getFullYear();
      let mm = new Date().getMonth() + 1;
      let dd = new Date().getDate();
      let hh = new Date().getHours();
      let mf =
        new Date().getMinutes() < 10
          ? "0" + new Date().getMinutes()
          : new Date().getMinutes();
      let ss =
        new Date().getSeconds() < 10
          ? "0" + new Date().getSeconds()
          : new Date().getSeconds();
      _this.gettime =
        yy + "年" + mm + "-" + dd + "日" + " " + hh + ":" + mf + ":" + ss;
    },

    currentTime() {
      setInterval(this.getTime, 500);
    },

  },
  components: {}
};
</script>

<style scoped >
.header {
  color: #c4d3ed;
  height: 60px;
  display: flex;
  text-align: center;
  padding: 10px 0;
}
.time {
  flex: 1;
  font-size: 12px;
}
.title {
  flex: 2;
}
.login {
  flex: 1;
}
.user {
  padding-left: 50px;
}
.user .el-button {
  color: #c4d3ed;
  border: 0;
  background-color: #09173d;
}
.nav {
  text-align: left;
}
.nav .el-button {
  color: #c4d3ed;
  border: 0;
  background-color: #334f9d;
}
</style>
