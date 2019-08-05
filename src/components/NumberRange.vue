<template>
    <div class="box">
        <input type="number" v-model="smallNum" @blur="smallBlur" />
        <span class="separator">{{ rangeSeparator }}</span>
        <input type="number" v-model="bigNum" @blur="bigBlur" />
        <span class="clear-icon-box" v-show="smallNum || bigNum" @click="clear">
            <i class="clear-icon"></i>
        </span>
    </div>
</template>
<script>
export default {
    data () {
        return {
            smallNum: this.min.toString() && Number(this.small) < Number(this.min) ? this.min : this.small,
            bigNum: this.max.toString() && Number(this.big) > Number(this.max) ? this.max : this.big,
            clearShow: false
        }
    },
    props: ['small', 'big', 'min', 'max', 'rangeSeparator'],
    methods: {
        smallBlur () {
            if (this.min.toString() && Number(this.smallNum) < Number(this.min)) { this.smallNum = this.min }
            else {
                // this.smallNum = Math.min(Number(this.smallNum), Number(this.max))
                if (this.smallNum.toString()) this.smallNum = Math.min(Number(this.smallNum), Number(this.max))
                this.$emit('update:small', this.smallNum)
            }
            this.bigBlur()
        },
        bigBlur () {
            if (this.max.toString() && Number(this.bigNum) > Number(this.max)) this.bigNum = this.max
            else {
                if (Number(this.smallNum) > Number(this.bigNum)) {
                    this.bigNum = this.smallNum
                }
                this.$emit('update:big', this.bigNum)
            }
        },
        clear () {
            this.smallNum = null
            this.bigNum = null
            this.$emit('update:small', null)
            this.$emit('update:big', null)
        }
    }
}
</script>
<style scoped>
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
}
input[type="number"] {
    -moz-appearance: textfield;
    border: 0;
    text-indent: 0.5em;
    width: 130px;
    outline: none;
}
.box {
    border: 1px solid #ccc;
    width: 300px;
    display: flex;
    height: 30px;
    align-items: center;
    padding-right: 6px;
}
.separator {
    width: 21px;
}
.box:hover .clear-icon-box {
    display: block;
}
.clear-icon-box {
    border: 1px solid #ccc;
    border-radius: 50%;
    width: 10px;
    height: 10px;
    display: none;
}
.clear-icon {
    display: inline-block;
    width: 6px;
    height: 1px;
    background: #333;
    line-height: 0;
    font-size: 0;
    vertical-align: 10px;
    transform: rotate(45deg);
}
.clear-icon:after {
    content: "/";
    display: block;
    width: 6px;
    height: 1px;
    background: #333;
    transform: rotate(-90deg);
}
</style>


