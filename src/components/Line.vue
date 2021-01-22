<template>
  <div class="b">
      Hless
  </div>
</template>

<script>
export default {
  name: "Line",
  props: {
    control_line:String,
    control_statu:Boolean,
  },
};
</script>

<style lang="less">
    .b{
        // position: relative;
        height: 50px;
        width: 50px;
        background: red;
        .bb{

        }
    }
</style>