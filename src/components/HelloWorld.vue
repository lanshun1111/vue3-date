<template>
  <div class="container">
    <el-date-picker
      v-model="value2"
      type="daterange"
      align="right"
      unlink-panels
      range-separator="至"
      start-placeholder="开始日期"
      end-placeholder="结束日期"
      :picker-options="pickerOptions"
      @click.stop
    >
    </el-date-picker>
    <div class="show">{{ value2 }}</div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      value2: null,
      pickerOptions: {
        shortcuts: [
          {
            text: "最近一周",
            onClick(picker) {
              picker.$emit("pick", "最近一周");
            }
          },
          {
            text: "最近一个月",
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
              picker.$emit("pick", [start, end]);
            }
          },
          {
            text: "最近三个月",
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
              picker.$emit("pick", [start, end]);
            }
          }
        ]
      }
    };
  }
};
</script>
<style lang="less" scoped>
.container {
  width: 100%;
  height: 100%;
  text-align: left;
  position: relative;
}
.container /deep/ .el-date-editor {
  opacity: 0;
  width: 200px;
}
.show {
  height: 60px;
  width: 200px;
  position: absolute;
  top: 0;
  z-index: -1;
  color: red;
  white-space: nowrap;
  overflow: hidden;
}
</style>
