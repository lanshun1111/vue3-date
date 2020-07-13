<template>
  <div class="leftNavContainer">
    <div class="listDate">
      <ul>
        <li v-for="(item, index) in defaultData" :key="index">
          {{ item.nameCn }}
        </li>
      </ul>
    </div>
    <div class="bottom">
      <button v-for="(item, index) in btn" :key="index">
        {{ item.nameCn }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    listDate: {
      type: Array,
      default: function() {
        return this.defaultData;
      }
    }
  },
  data() {
    return {
      defaultData: [
        {
          nameCn: "三个月",
          nameEn: ""
        },
        {
          nameCn: "三个月",
          nameEn: ""
        },
        {
          nameCn: "三个月",
          nameEn: ""
        }
      ],
      btn: [
        {
          nameCn: "取消",
          nameEn: ""
        },
        {
          nameCn: "关闭",
          nameEn: ""
        }
      ]
    };
  }
};
</script>


<style lang="less" scoped>
.leftNavContainer {
  height: 250px;
  width: 200px;
  display: inline-block;
  clear: both;
  overflow: hidden;
  .listDate {
    height: calc(100% - 40px);
    width: 100%;
    display: inline-block;
  }
  ul {
    display: inline-block;
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
  }
  li {
    display: inline-block;
    width: 100%;
    white-space: nowrap;
    text-decoration: none;
    cursor: pointer;
    height: 30px;
    line-height: 30px;
    text-align: left;
    background: lightblue;
  }
  .bottom {
    display: inline-flex;
    width: 100%;
    height: 40px;
    justify-content: flex-end;
  }
}
</style>