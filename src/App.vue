<script>
import { defineComponent } from 'vue';

import Main from './components/Main.vue'

export default defineComponent({

    components: {Main},

})
</script>

<template>
    <div class="container font-lucida pt-[1em] w-fit m-auto bg-green-900 md:w-[600px]">
        <header>
            <p class="text-[1.5em] font-medium text-white py-[0.5em] px-[1.5em] text-center leading-[1.2]">Jagtech App <span class="font-bold">4</span> Contribution</p>
            <!-- MAIN -->
           <Main />
            
        </header>
    </div>
</template>

<style>


</style>