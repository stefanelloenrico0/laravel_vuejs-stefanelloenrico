<script setup>
    import { ref, onMounted } from 'vue';

    import Button from "primevue/button"
    import Drawer from 'primevue/drawer';

    let visible = ref(false);
    let cardsMenu = ref(null);

    function setDrawerVisibility(){
        visible.value = !visible.value;
    }
    onMounted(() => {
        console.log('Application has started');
        cardsMenu.value = [
            {
                'id': '0',
                'name': 'movies',
                'icon': '<fa-icon :icon="fa-regular fa-user" />'
            }
        ];
    })
</script>

<template>
    <div>
        <div id="headerSection" class="h-[80px]">
            <Button id="btnOpenSidebar" icon="pi pi-align-justify" class="absolute top-0 left-0 border-rad !rounded-none h-[40px] w-[40px] bg-siteDefault" @click="setDrawerVisibility"></Button>
        </div>
        <Drawer v-model:visible="visible" header="Menu" class="h-[calc(100%-40px)] top-[40px]">
            <div id="userDrawerActions" class="w-full flex justify-center">
                <i id="user" class="pi pi-user cursor-pointer" @click="userDetails"></i>
                <i id="logout" class="pi pi-sign-out cursor-pointer hover:bg-siteDefault" @click="logoutUser"></i>
            </div>
        </Drawer>
        <div id="pagesMenu" class="w-full flex justify-start pl-8">
            <div id="cardsContainer" class="grid grid-cols-4 gap-4">
                <div :id="'card_'+card.id" class="flex flex-col" v-for="card in cardsMenu" :key="card.id">
                    <div v-html="card.icon" />
                    <i class="far fa-user" />
                </div>
            </div>
        </div>
    </div>
</template>
