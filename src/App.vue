<template>
    <div id="app">
        <NumberRange :small.sync="small" :big.sync="big" :min="range[0]" :max="range[1]" rangeSeparator="~" />
    </div>
</template>

<script>
import NumberRange from './components/index'

export default {
    name: 'app',
    data () {
        return {
            small: null,
            big: null,
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
