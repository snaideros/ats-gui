<template>
  <div class="bg-teal" ref="ide" id="ide"></div>
</template>
  
<script setup>
  import * as monaco from 'monaco-editor/esm/vs/editor/editor.api';
  import { LoremIpsum } from "lorem-ipsum";
  import { ref, onMounted } from 'vue';

  const ide = ref();
  const lorem = new LoremIpsum({
    sentencesPerParagraph: {
      max: 8,
      min: 4
    },
    wordsPerSentence: {
      max: 16,
      min: 4
    }
  });
  const text = lorem.generateParagraphs(120);

  onMounted(() => {
  monaco.editor.create(ide.value, {
    value: text,
  })
});
</script>

<style scoped>
#ide {
  height: 100%;
}
</style>
