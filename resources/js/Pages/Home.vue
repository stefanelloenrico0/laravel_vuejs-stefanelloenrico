<script setup>
    import { onMounted } from 'vue';

    import Button from "primevue/button"
    import * as gbFunc from '../functions.js';

    onMounted(() => {
        console.log('Application has started');

        document.querySelector('#titleHomepage').classList.add('opacity-100');
        document.querySelector('#titleHomepage').classList.add('-translate-y-[0]');
    })
</script>

<template>
    <div>
        <div id="homepage" class="w-full h-full">
            <div class="w-full h-full flex ">
                <h1 id="titleHomepage" class="opacity-0 -translate-y-[-150%] transition duration-1000 ease-in-out w-[75%]">
                    <b>WELCOME,</b> <br/>I'm Stefanello Enrico!
                </h1>
                <div id="rowButtonsHome" class="w-[25%] flex flex-col justify-center align-baseline">
                    <div class="flex" style="align-items: center;gap: 15px;">
                        <fa-icon :icon="['fas', 'right-to-bracket']" class="fa-beat" style="height: 2em;"/><Button class="w-[50%]">Download CV</Button>
                    </div>
                    <div class="flex" style="align-items: center;gap: 15px;">
                        <fa-icon :icon="['fas', 'right-to-bracket']" class="fa-beat" style="height: 2em;"/><Button class="w-[50%]">See Projects</Button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
