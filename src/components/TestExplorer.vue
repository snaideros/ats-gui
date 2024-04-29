<template>
    <div class="bg-white extra-height">
        <v-list
            v-model:opened="open"
            open-strategy="multiple"
            v-model:selected="select"
            select-strategy="single-leaf"
            theme="light"
            density="compact"
            :items="treeData"
        ></v-list>
        <div>
            <h3>Opened hierarchy</h3>
            {{ open }}
        </div>
        <div>
            <h3>Selected File</h3>
            {{ select }}
        </div>
    </div>
</template>

<script setup>
// Right click from https://vuejs.org/examples/#circle-drawer
import { ref } from 'vue';

const open = ref([]);

const select = ref([]);

// Array must be fetched with right alphabetical order
// Use default keys understood by v-list
const treeData = ref([{
    title: 'hello',
    value: 'hello',
    gitStatus: '',
    edited: false,
}, {
    title: 'world',
    value: 'world',
    gitStatus: '',
    edited: false,
}, {
    title: 'dir1',
    value: 'dir1',
    children: [{
        title: 'dir2',
        value: 'dir1/dir2',
        children: [{
            title: 'hello',
            value: 'dir1/dir2/hello',
            gitStatus: '',
            edited: false,
        }, {
            title: 'world',
            value: 'dir1/dir2/world',
            gitStatus: '',
            edited: false,
        }]
    }, {
        title: 'hello',
        value: 'dir1/hello',
        gitStatus: '',
        edited: false,
    }, {
        title: 'world',
        value: 'dir1/world',
        gitStatus: '',
        edited: false,
    }, {
        title: 'dir3',
        value: 'dir1/dir3',
        children: [{
            title: 'hello',
            value: 'dir1/dir3/hello',
            gitStatus: '',
            edited: false,
        }, {
            title: 'world',
            value: 'dir1/dir3/world',
            gitStatus: '',
            edited: false,
        }],
    }]
}]);
</script>

<style scoped>
.extra-height {
    height: 2000px;
}
</style>
