<template>
    <div class="child-page">
        这是父组件传递的值:{{refTst}}
    </div>
</template>
<script>
import { defineComponent } from 'vue';
// import { reactive, ref } from '@vue/composition-api';
export default defineComponent({
    props: ['refTst'],
    setup(props, context) {
        console.log(props.refTst, context);
        return {
            // propVal1
        };
    }
});
</script>
<style>

</style>
