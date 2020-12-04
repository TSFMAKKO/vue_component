<template>
  <div class="hello">
    <div>ERROR 找不到網頁</div>
    <div>{{ who }} [{{ title }}]</div>
  </div>
</template>

<script>
// export default{
//     data:function(){
//         return {
//             who:'world'
//         }
//     }
// }

let err_timer;

module.exports = {
  data: function () {
    return {
      who: "world",
    };
  },
  props: ["title"],
  beforeCreate() {
    console.log("beforeCreate");

    let timer = setTimeout(() => {
      // history.pushState('','','/');
      this.$router.push("/");
    }, 3000);

    this.$emit("err_timer", timer);
  },
  created() {
    console.log("created1");
  },
  updated() {
    console.log("updated1");
  },
  //   beforeDestory() {
  //     console.log("銷毀完成前");
  //     console.log(timer);
  //     clearTimeout(timer);
  //   },
  //   destoryed() {
  //     console.log("destoryed銷毀完成");
  //     console.log(timer);
  //     clearTimeout(timer);
  //   },
};
</script>

<style scoped>
.hello {
  background-color: green;
}
</style>
