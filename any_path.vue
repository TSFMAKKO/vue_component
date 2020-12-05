<template>
  <!-- <transition name="fade" mode="out-in"> -->
    <div>{{ anyPath }}(隨意路徑)</div>
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

// 不用先宣告 let module = {}
// modult.exports = {}

module.exports = {
  data() {
    return {
      anyPath: "any_path",
    };
  },
  methods: {
    getPath() {
      // console.log(this.$route.fullPath);
      console.log("query:", this.$route.query);
      //   this.anyPath = this.$route.params.pathMatch;
      let fullPath = this.$route.fullPath;
      this.anyPath = fullPath;

      console.log(this.anyPath);
    },
  },
  //   beforeCreate()
  created() {
    //   this.anyPath = this.$route.params.pathMatch;
    //   console.log(this.anyPath);
    this.getPath();
  },

  watch: {
    // $route(to, from) {
    //   console.log(to, from);
    //   this.getPath();
    //   console.log("抓取api寫入data");
    // },
  },

  beforeRouteUpdate(to, from, next) {
    console.log("beforeRouteUpdate", to, from);
    let query = to.query;
    let params = to.params;
    let fullPath = to.fullPath;
    console.log(fullPath);
    // console.log(query);
    this.anyPath = fullPath;

    // this.getPath();
    // console.log("抓取api寫入data");
    // 要next()還會觸發dom/template/this.$route週期重新整理
    next();
  },
};
</script>


<style scoped>
/* scoped */

</style>
