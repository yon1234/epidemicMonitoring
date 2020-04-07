<template>
  <div class="showNum">
    <div class="nowNum">
      <div
        :class="[color==1?'orange':'',color==2?'red':'',color==3?'yellow':'',color==4?'blue':'','num']"
      >{{nums}}</div>
      <span>{{typeNum}}</span>
    </div>
    <div class="addnum">较昨日+{{addNums}}</div>
  </div>
</template>

<script>
export default {
  props: ["nums", "addNums", "color", "typeNum"],
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
.showNum {
  width: 60%;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: white;
  text-align: center;
}
.nowNum {
  width: 100%;
  background-color: #101464;
  opacity: 0.8;
  height: 100px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  box-shadow: 0px 1px 4px 1px rgb(63, 125, 233);
  border-radius: 5px;
  background: linear-gradient(to left, #3d73ac, #3d73ac) left top no-repeat,
    linear-gradient(to bottom, #3d73ac, #3d73ac) left top no-repeat,
    linear-gradient(to left, #3d73ac, #3d73ac) right top no-repeat,
    linear-gradient(to bottom, #3d73ac, #3d73ac) right top no-repeat,
    linear-gradient(to left, #3d73ac, #3d73ac) left bottom no-repeat,
    linear-gradient(to bottom, #3d73ac, #3d73ac) left bottom no-repeat,
    linear-gradient(to left, #3d73ac, #3d73ac) right bottom no-repeat,
    linear-gradient(to left, #3d73ac, #3d73ac) right bottom no-repeat;
  background-size: 3px 20px, 20px 3px, 3px 20px, 20px 3px;
}
.nowNum span {
  font-size: 14px;
}
.num {
  height: 32px;
  font-size: 20px;

  width: 80%;
  line-height: 32px;
}
.addnum {
  width: 60%;
  height: 28px;
  line-height: 28px;
  font-size: 12px;
  box-shadow: 0px 1px 4px 1px rgb(63, 125, 233);
}
.orange {
  color: orange;
  background: linear-gradient(to left, orange, orange) left top no-repeat,
    linear-gradient(to bottom, orange, orange) left top no-repeat,
    linear-gradient(to left, orange, orange) right top no-repeat,
    linear-gradient(to bottom, orange, orange) right top no-repeat,
    linear-gradient(to left, orange, orange) left bottom no-repeat,
    linear-gradient(to bottom, orange, orange) left bottom no-repeat,
    linear-gradient(to left, orange, orange) right bottom no-repeat,
    linear-gradient(to left, orange, orange) right bottom no-repeat;
  background-size: 3px 20px, 10px 3px, 3px 20px, 10px 3px;
  background-color: #392b38;
}
.red {
  color: #f00;
  background: linear-gradient(to left, #f00, #f00) left top no-repeat,
    linear-gradient(to bottom, #f00, #f00) left top no-repeat,
    linear-gradient(to left, #f00, #f00) right top no-repeat,
    linear-gradient(to bottom, #f00, #f00) right top no-repeat,
    linear-gradient(to left, #f00, #f00) left bottom no-repeat,
    linear-gradient(to bottom, #f00, #f00) left bottom no-repeat,
    linear-gradient(to left, #f00, #f00) right bottom no-repeat,
    linear-gradient(to left, #f00, #f00) right bottom no-repeat;
  background-size: 3px 20px, 10px 3px, 3px 20px, 10px 3px;
  background-color: #783333;
}
.yellow {
  color: yellow;
  background: linear-gradient(yellow, yellow, yellow) left top no-repeat,
    linear-gradient(to bottom, yellow, yellow) left top no-repeat,
    linear-gradient(to left, yellow, yellow) right top no-repeat,
    linear-gradient(to bottom, yellow, yellow) right top no-repeat,
    linear-gradient(to left, yellow, yellow) left bottom no-repeat,
    linear-gradient(to bottom, yellow, yellow) left bottom no-repeat,
    linear-gradient(to left, yellow, yellow) right bottom no-repeat,
    linear-gradient(to left, yellow, yellow) right bottom no-repeat;
  background-size: 3px 20px, 10px 3px, 3px 20px, 10px 3px;
  background-color: #8e9d60;
}
.blue {
  color: #21eddf;
  background: linear-gradient(to left, #21eddf, #21eddf) left top no-repeat,
    linear-gradient(to bottom, #21eddf, #21eddf) left top no-repeat,
    linear-gradient(to left, #21eddf, #21eddf) right top no-repeat,
    linear-gradient(to bottom, #21eddf, #21eddf) right top no-repeat,
    linear-gradient(to left, #21eddf, #21eddf) left bottom no-repeat,
    linear-gradient(to bottom, #21eddf, #21eddf) left bottom no-repeat,
    linear-gradient(to left, #21eddf, #21eddf) right bottom no-repeat,
    linear-gradient(to left, #21eddf, #21eddf) right bottom no-repeat;
  background-size: 3px 20px, 10px 3px, 3px 20px, 10px 3px;
  background-color: #4d7684;
}
</style>
