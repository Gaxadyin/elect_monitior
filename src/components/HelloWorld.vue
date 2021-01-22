<template>
  <div class="hello" >
    <!-- <h1>{{ msg }}</h1> -->
    <div
      class="bb"
      :class="{ openbottom:control_heng_statu=='True'&&control_line[0] == '1',openright:control_shu_statu=='True'&&control_line[1] == '1',lbott: control_line[0] == '1', lright: control_line[1] == '1',}"
    ></div>
    <div
      class="bb"
      :class="{openbottom:control_heng_statu=='True'&& control_line[3] == '1',openleft:control_shu_statu=='True'&&control_line[2] == '1' , lleft: control_line[2] == '1', lbott: control_line[3] == '1',}"
    ></div>
    <div
      class="bb"
      :class="{ opentop:control_heng_statu=='True'&&control_line[4] == '1',openright:control_shu_statu=='True'&&control_line[5] == '1',ltop: control_line[4] == '1', lright: control_line[5] == '1', }"
    ></div>
    <div
      class="bb"
      :class="{ opentop:control_heng_statu=='True'&&control_line[7] == '1',openleft:control_shu_statu=='True'&&control_line[6] == '1',lleft: control_line[6] == '1', ltop: control_line[7] == '1' ,}"
    ></div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    control_line: String,
    control_heng_statu: String,
    control_shu_statu: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


.hello {
  height: 40px;
  width: 40px;
  /* background: red; */
  position: relative;
  border-color: gray;;
}
.bb {
  float: left;
  height: 20px;
  width: 20px;
  left: 0;
  background: white;
}
.lbott {
  /* background: tomato; */
  height: 19px;
  border-bottom-style: dotted;
  border-bottom-width: 1px;
  border-color: rgb(194, 192, 192);
}
.lright {
  /* background: tomato; */
  width: 19px;
  border-right-style:dotted;
  border-right-width: 1px;
  border-color: rgb(194, 192, 192);
  /* border-color: tomato; */
}
.lleft {
  /* background: tomato; */
  width: 19px;
  border-left-style: dotted;
  border-left-width: 1px;
  border-color: rgb(194, 192, 192);
  /* border-color: tomato; */
}
.ltop {
  /* background: tomato; */
  height: 19px;
  border-top-style: dotted;
  border-top-width: 1px;
  border-color: rgb(194, 192, 192);
  /* border-color: tomato; */
}
.openleft {
  width: 17px;
  border-left-style: solid;
  border-left-width: 3px;
  border-left-color:black;
}
.openright {
 width: 17px;
  border-right-style: solid;
  border-right-width: 3px;
  border-right-color: black;
}
.opentop{
  height: 17px;
  border-top-style: solid;
  border-top-width: 3px;
  border-top-color:black;
}
.openbottom {
  height: 17px;
  border-bottom-style: solid;
  border-bottom-width: 3px;
  border-bottom-color: black;
}
</style>
