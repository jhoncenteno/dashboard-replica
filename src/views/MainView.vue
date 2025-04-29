<script setup>
import Sidebar from '../components/Sidebar.vue';
import TopBar from '../components/TopBar.vue';
import Dashboard from '../modules/Dashboard/Dashboard.vue';
</script>

<template>
    <div class="flex">
        <Sidebar />
        <div class="flex-1 flex flex-col">
            <TopBar />
            <div class="flex-1 py-11 px-9 bg-gray-100 overflow-auto">
                <Dashboard />
            </div>
        </div>
    </div>
</template>

<style scoped></style>
