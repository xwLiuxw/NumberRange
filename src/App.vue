<template>
    <div id="app">
        <VueNumberRange :small.sync="small" :big.sync="big" :min="range[0]" :max="range[1]"  rangeSeparator="~" placeholder="价格"/>
    </div>
</template>

<script>
import VueNumberRange from './components/index'

export default {
    name: 'app',
    data () {
        return {
            small: 10,
            big: 20,
            range: [0, 100]
        }
    },
    components: {
        VueNumberRange
    }
}
</script>

<style>
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
