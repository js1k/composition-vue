<template>
<div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <div>{{refTst}}</div>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { reactive, ref } from '@vue/composition-api';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
    name: 'Home',
    components: {
        // eslint-disable-next-line vue/no-unused-components
        HelloWorld
    },
    setup(props, context) {
        const refTst = ref(0);
        console.log(props, context);
        // let txt = 123;
        function testReactive() {
            setInterval(() => {
                // txt++;
                refTst.value += 1;
                console.log(refTst);
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
