<template>
    <div id="app">
        <NumberRange :small.sync="small" :big.sync="big"  rangeSeparator="~" placeholder="价格"/>
    </div>
</template>

<script>
import NumberRange from './components/index'

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
        NumberRange
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
