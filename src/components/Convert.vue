<template>
  <div class="convert">
    <h2>{{coinA}} Para {{coinB}}</h2> 
    <input type="text" v-model="coinA_value" v-bind:placeholder="coinA">
    <input type="button" value="Converter" v-on:click="convert">
    <h2>{{coinB_value}}</h2>
  </div>
</template>

<script>
export default {
    name: 'Convert', 
    props: ["coinA", "coinB"], 
    data() {
        return {
            coinA_value: "",
            coinB_value: 0,
        }
    },
    methods: {
        convert() {
            let from_to = this.coinA + "_" + this.coinB;

            let url = "http://free.currencyconverterapi.com/api/v5/convert?q=" +
                from_to
            + "&compact=y";

            fetch(url).then(res => { return res.json() })
                .then(json => {
                    let quote = json[from_to].val;
                    this.coinB_value = (quote * parseFloat(this.coinA_value)).toFixed(2);
                })
        }
    }
}
</script>

<style scoped>
    .convert {
        padding: 20px;
        max-width: 300px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    }
</style>