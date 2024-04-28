<template>
    <div class="bg-orange">
        <ul>
            <TreeItem
                class="item"
                v-for="model in treeData"
                :model="model">
            </TreeItem>
        </ul>
    </div>
</template>

<script setup>
// Tree from https://vuejs.org/examples/#tree
// Right click from https://vuejs.org/examples/#circle-drawer
import { ref } from 'vue';

const treeData = ref([
    { name: 'hello' },
    { name: 'world' },
    {
        name: 'child folder',
        children: [
        {
            name: 'child folder',
            children: [{ name: 'hello' }, { name: 'world' }]
        },
        { name: 'hello' },
        { name: 'world' },
        {
            name: 'child folder',
            children: [{ name: 'hello' }, { name: 'world' }]
        }
        ]
    }
]);
</script>

<style scoped>
</style>
