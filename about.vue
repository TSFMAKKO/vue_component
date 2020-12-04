<template>
  <div class="hello">
    <div>about {{ who }} [{{ title }}]</div>

    <form action="" @submit="submitHandler">
      <input type="text" v-model="inputVal" name="inputVal" />
      <input type="submit" value="submit" />
    </form>
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

// 不用先宣告 let module = {}
// modult.exports = {}

module.exports = {
  data: function () {
    return {
      who: "world",
      inputVal: "",
    };
  },
  props: ["title", "timer1"],
  methods: {
    submitHandler(e) {
      console.log("submitHandler");
      console.log(e);
      console.log(this.inputVal);
      e.preventDefault();
      this.$emit("update", this.inputVal);
    },
  },
  beforeCreate() {
    console.log("beforeCreate2");
  },
  created() {
    console.log("created2");
    console.log(this.inputVal);
    console.log(this.title);
    console.log(this.timer1);
    clearInterval(this.timer1);
  },
  updated() {
    console.log("updated2");
    this.$emit("update", this.inputVal);
  },
};
</script>

<style scoped>
.hello {
  background-color: red;
}
</style>
