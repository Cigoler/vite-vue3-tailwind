<script setup>
import Header from '@/components/Header.vue'
import Sidebar from '@/components/Sidebar.vue'
</script>

<template>
    <div>
        <Header/>
        <main>

            <Sidebar/>
            <router-view />
        </main>
    </div>
</template>
