<script setup>
    import { ref, onMounted } from 'vue';

    import Button from "primevue/button"
    import Drawer from 'primevue/drawer';

    let visible = ref(false);

    function setDrawerVisibility(){
        visible.value = !visible.value;
    }
    onMounted(() => {
        console.log('Application has started')
    })
</script>

<template>
    <div>
        <Button id="btnOpenSidebar" icon="pi pi-align-justify" class="absolute top-0 left-0 border-rad !rounded-none" @click="setDrawerVisibility"></Button>
        <Drawer v-model:visible="visible" header="Menu">
            <div id="userDrawerActions" class="w-full flex justify-center">
                <i id="user" class="pi pi-user cursor-pointer" @click="userDetails"></i>
                <i id="logout" class="pi pi-sign-out cursor-pointer hover:bg-siteDefault" @click="logoutUser"></i>
            </div>
        </Drawer>
    </div>
</template>
