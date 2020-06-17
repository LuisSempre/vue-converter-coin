<template>
  <div class="coin">
    <h2>{{coinA}} for {{coinB}}</h2>
    <input type="text" v-model="coinA_value" v-bind:placeholder="coinA" />
    <input type="button" value="Converter" v-on:click="converter" />
    <h2>{{coinB_value}}</h2>
  </div>
</template>

<script>
export default {
  name: "Converter",
  props: ["coinA", "coinB"],
  data() {
    return {
      coinA_value: "",
      coinB_value: 0
    };
  },
  methods: {
    converter() {
      let d_for = this.coinA + "_" + this.coinB;

      let url =
        "https://free.currconv.com/api/v7/convert?q="
        +d_for+ 
        "&compact=y&apiKey=b740d5ee3a9289d74fe8"

      fetch(url)
        .then(res => {
            
          return res.json();
        })
        .then(json => {
            console.log(json)
          let cot = json[d_for].val;
          this.coinB_value = (cot * (this.coinA_value)).toFixed(2)
        })
    }
  }
};
</script>

<style scoped>
* {
  color: white;
}
</style>