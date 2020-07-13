<template>
  <div class="home">
    <HelloWorld />
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld1.vue";
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  mounted() {
    let c = 1;
  }
};
</script>

<style lang="less" scoped>
.home {
  width: 100%;
  height: 100%;
}
</style>
