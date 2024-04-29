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

const treeData = ref([{
    name: 'hello',
    gitStatus: '',
    edited: false,
}, {
    name: 'world',
    gitStatus: '',
    edited: false,
}, {
    name: 'child folder',
    children: [{
        name: 'child folder',
        children: [{
            name: 'hello',
            gitStatus: '',
            edited: false,
        }, {
            name: 'world',
            gitStatus: '',
            edited: false,
        }]
    }, {
        name: 'hello',
        gitStatus: '',
        edited: false,
    }, {
        name: 'world',
        gitStatus: '',
        edited: false,
    }, {
        name: 'child folder',
        children: [{
            name: 'hello',
            gitStatus: '',
            edited: false,
        }, {
            name: 'world',
            gitStatus: '',
            edited: false,
        }],
    }]
}]);
</script>

<style scoped>
</style>
