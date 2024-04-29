<template>
  <v-container class="bg-cyan fill-height pa-0" fluid>
      <v-row class="flex-column bg-pink fill-height" no-gutters>
          <v-col class="bg-deep-purple flex-shrink-1 flex-grow-0">
              <v-breadcrumbs class="bg-yellow"></v-breadcrumbs>
          </v-col>
          <v-col class="bg-indigo">
              <v-row class="bg-purple fill-height" no-gutters>
                  <v-col cols="2" class="bg-red" style="position:relative;">
                      <div class="bg-green pa-1" style="position:absolute;top:0;left:0;right:0;bottom:0;overflow-y: auto;">
                          <TestExplorer/>
                      </div>
                  </v-col>
                  <v-col cols="10" class="bg-blue" style="position:relative;">
                      <div class="bg-lime pa-1" style="position:absolute;top:0;left:0;right:0;bottom:0;">
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

<route>
{
  meta: {
      layout: false
  },
}
</route>