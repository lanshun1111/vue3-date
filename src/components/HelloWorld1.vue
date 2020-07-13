<template>
  <div class="coantainer">
    <div class="date-picker" @click.stop>
      <input
        class="input"
        v-model="dateValue"
        @click.stop.prevent="openPanel"
      />
      <transition name="fadeInDownBig">
        <div class="dateContainer clear">
          <DataNav />
          <Data />
          <Data />
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import Data from "./date";
import DataNav from "./leftNav";
export default {
  components: {
    Data,
    DataNav
  },
  data() {
    return {
      panelState: false,
      dateValue: ""
    };
  },
  mounted() {}
};
</script>

<style lang='less' scoped>
.clear {
  clear: both;
}
.coantainer {
  width: 100%;
  height: 100%;
  text-align: left;
  position: relative;
  background: #ffffff;
}
.dateContainer {
  display: inline-flex;
  height: auto;
  width: auto;
  position: absolute;
  top: 40px;
  left: 0;
  background: #fafafa;
  padding: 5px;
  box-shadow: 0 0 2px rgba(225, 225, 225, 0.8);
}
input {
  display: inline-block;
  box-sizing: border-box;
  width: 100%;
  height: 32px;
  line-height: 1.5;
  padding: 4px 7px;
  font-size: 12px;
  border: 1px solid #cccccc;
  border-radius: 4px;
  color: #515a6e;
  background-color: #fff;
  background-image: none;
  position: relative;
  cursor: text;
  width: 200px;
  transition: border 0.2s ease-in-out, background 0.2s ease-in-out,
    box-shadow 0.2s ease-in-out;
  margin-bottom: 6px;
  outline: none;
}
.fadeDownBig-enter-active,
.fadeDownBig-leave-active,
.fadeInDownBig {
  -webkit-animation-duration: 0.5s;
  animation-duration: 0.5s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}
.fadeDownBig-enter-active {
  -webkit-animation-name: fadeInDownBig;
  animation-name: fadeInDownBig;
}
.fadeDownBig-leave-active {
  -webkit-animation-name: fadeOutDownBig;
  animation-name: fadeOutDownBig;
}
@-webkit-keyframes fadeInDownBig {
  from {
    opacity: 0.8;
    -webkit-transform: translate3d(0, -4px, 0);
    transform: translate3d(0, -4px, 0);
  }
  to {
    opacity: 1;
    -webkit-transform: none;
    transform: none;
  }
}
@keyframes fadeInDownBig {
  from {
    opacity: 0.8;
    -webkit-transform: translate3d(0, -4px, 0);
    transform: translate3d(0, -4px, 0);
  }
  to {
    opacity: 1;
    -webkit-transform: none;
    transform: none;
  }
}
@-webkit-keyframes fadeOutDownBig {
  from {
    opacity: 1;
  }
  to {
    opacity: 0.8;
    -webkit-transform: translate3d(0, -4px, 0);
    transform: translate3d(0, -4px, 0);
  }
}
@keyframes fadeOutDownBig {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
</style>