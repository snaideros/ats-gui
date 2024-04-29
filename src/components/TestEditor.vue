<template>
    <v-container class="bg-cyan fill-height pa-0" fluid>
        <v-row class="flex-column bg-pink fill-height" no-gutters>
            <v-col class="bg-deep-purple flex-shrink-1 flex-grow-0">
                <v-breadcrumbs class="bg-yellow"></v-breadcrumbs>
            </v-col>
            <v-col class="bg-indigo">
                <v-row class="bg-purple fill-height" no-gutters>
                    <v-col cols="2" class="bg-red rel">
                        <div class="bg-green pa-1 abs" style="overflow-y: auto;">
                            <TestExplorer/>
                        </div>
                    </v-col>
                    <v-col cols="10" class="bg-blue rel">
                        <div class="bg-lime pa-1 abs">
                            <IDE/>
                        </div>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>
  
<script setup>
  //
</script>
  
<style>
  .rel {
    position: relative;
  }
  
  .abs {
    position:absolute;
    top:0;
    left:0;
    right:0;
    bottom:0;
  }
</style>
  