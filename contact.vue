<template>
  <div class="hello">home {{ who }} [{{ title }}]</div>
</template>

<script>
// export default{
//     data:function(){
//         return {
//             who:'world'
//         }
//     }
// }

module.exports = {
  data: function () {
    return {
      who: "world",
    };
  },
  props: ["title"],
  beforeCreate() {
    console.log("beforeCreate1");
  },
  created() {
    console.log("created1");
  },
  updated() {
    console.log("updated1");
  },
};
</script>

<style scoped>
.hello {
  background-color: green;
}
</style>
