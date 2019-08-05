# vue-number-range

## vue-number-range
```
数字范围输入组件
```

### Install
```
npm i -S number-range
```

### Preview

```
```

### Usage

```
<template>
    <div id="app">
        <NumberRange :small.sync="small" :big.sync="big" :min="range[0]" :max="range[1]"  rangeSeparator="~" placeholder="价格"/>
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

```


