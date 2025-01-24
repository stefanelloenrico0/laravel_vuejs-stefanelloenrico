<script setup>
    import { onMounted } from 'vue';

    import Button from "primevue/button"
    import * as gbFunc from '../functions.js';

    onMounted(() => {
        console.log('Application has started');

        document.querySelector('#titleHomepage').classList.add('opacity-1 -translate-y-[0]');
    })
</script>

<template>
    <div>
        <div id="homepage" class="w-full h-full opacity-0 -translate-y-[-150%] transition duration-500 ease-in-out">
            <h1 id="titleHomepage"><b>WELCOME</b>, I'm Stefanello Enrico!</h1>
        </div>
    </div>
</template>
