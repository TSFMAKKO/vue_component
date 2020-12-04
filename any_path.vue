<template>
  <div>/about/{{ anyPath }}(隨意路徑)</div>
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
      this.anyPath = this.$route.params.pathMatch;
      console.log(this.anyPath);
    },
  },
  created() {
    //   this.anyPath = this.$route.params.pathMatch;
    //   console.log(this.anyPath);
    this.getPath();
  },

  watch: {
    $route(to, from) {
      console.log(to, from);
      this.getPath();
      console.log("抓取api寫入data");
    },
  },
};
</script>

<style scoped>
</style>
