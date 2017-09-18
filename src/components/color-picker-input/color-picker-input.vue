<template>
<div :class="classes">
    <div :class="wrapClasses">
        <color-picker v-model="currentValue"></color-picker>
        <input type='text' v-model="currentValue" :class="inputClasses">
    </div>
</div>
</template>
<script>
import ColorPicker from '../color-picker/color-picker.vue';
import Emitter from '../../mixins/emitter';
const prefixCls = 'bsc-color-picker-input';
const isColor = (color) => {
    const regHex6 = /^#([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i;
    const regHex3 = /^#([a-f\d])([a-f\d])([a-f\d])$/i;
    return regHex6.test(color) || regHex3.test(color);
};
export default {
    name: 'ColorPickerInput',
    mixins: [ Emitter ],
    props: {
        value: {
            type: String,
        }
    },
    data () {
        return {
            prefixCls: prefixCls,
            currentValue: this.value
        };
    },
    computed: {
        colorError () {
            return !isColor(this.currentValue);
        },
        classes () {
            return [
                `${prefixCls}`
            ];
        },
        wrapClasses () {
            return [
                `${prefixCls}-wrap`,
                {
                    [`${prefixCls}-error`]: this.colorError
                }
            ];
        },
        inputClasses () {
            return [
                `${prefixCls}-write`
            ];
        }
    },
    component: { ColorPicker },
    methods: {
        
    },
    watch: {
        currentValue (color) {
            this.$emit('input', color);
        }
    }
};
</script>
