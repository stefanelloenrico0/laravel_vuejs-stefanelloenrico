<script setup>
    import { ref, onMounted } from 'vue';

    import Button from "primevue/button"
    import DrawerMenu from "@/Components/DrawerMenu.vue";
    import * as gbFunc from '../functions.js';

    let visible = ref(false);
    let cardsMenu = ref(null);

    function setDrawerVisibility(){
        visible.value = !visible.value;
    }
    function closeDrawerMenu(){
        visible.value = false;
    }
    onMounted(() => {
        console.log('Application has started');
        cardsMenu.value = [
            {
                'id': '0',
                'name': 'movies',
                'icon': 'fa-solid fa-film'
            },
            {
                'id': '1',
                'name': 'music',
                'icon': 'fa-solid fa-headphones'
            }
        ];
    })
</script>

<template>
    <div>
        <div id="headerSection" class="h-[80px]">
            <Button id="btnOpenSidebar" icon="pi pi-align-justify" class="absolute top-0 left-0 border-rad !rounded-none h-[40px] w-[40px] bg-siteDefault" @click="setDrawerVisibility"></Button>
        </div>
        <DrawerMenu :visible="visible" :cardsMenu="cardsMenu" @closeDrawerMenu="closeDrawerMenu"/>
        <div id="pagesMenu" class="w-full flex justify-start pl-8 h-[calc(100%-80px)]">
            <div id="cardsContainer" class="grid grid-cols-4 gap-4 w-full">
                <div :id="'card_'+card.id" class="flex flex-col homeCards" v-for="card in cardsMenu" :key="card.id">
                    <fa-icon :icon="card.icon" class="text-2xl"/>
                    <h2 class="text-center text-2xl">{{gbFunc.capitalizeFirstLetter(card.name)}}</h2>
                </div>
            </div>
        </div>
    </div>
</template>
