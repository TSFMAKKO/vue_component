<template>
  <!-- <transition name="fade"> -->
  <div class="hello">home {{ who }} [{{ title }}]</div>
  <!-- </transition> -->
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
/* scoped */
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
.hello {
  background-color: green;
}

</style>
