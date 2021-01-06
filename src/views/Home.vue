<template>
<div class="home">
    <div>{{refTst}}</div>
    <child :refTst="refTst"/>
</div>
</template>

<script lang="ts">
import child from './child.vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
    name: 'Home',
    components: {
        child
    },
    setup() {
        const refTst = ref(0);
        // let txt = 123;
        function testReactive() {
            setInterval(() => {
                // txt++;
                refTst.value += 1;
                // console.log(refTst);
            }, 1000);
        }
        testReactive();
        function clickTest() {
            console.log('clickTest');
        }
        return {
            refTst, clickTest
        };
    }
});
</script>
