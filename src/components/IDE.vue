<template>
  <div class="bg-teal" ref="ide" id="ide"></div>
</template>
  
<script setup>
  import * as monaco from 'monaco-editor/esm/vs/editor/editor.api';
  import { LoremIpsum } from "lorem-ipsum";
  import { ref, onMounted } from 'vue';

  // Reference to the #ide DOM element
  const ide = ref(null);

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

  let editor;
  const setIdeSize = function setIdeSize() {
    editor.layout({
      width: ide.value.offsetWidth,
      height: ide.value.offsetHeight,
    });
  };

  monaco.editor.onDidCreateEditor(() => {
    setTimeout(setIdeSize,0);
  });

  onMounted(() => {
    editor = monaco.editor.create(
      ide.value,
      {
        value: lorem.generateParagraphs(120),
      },
    );
    window.addEventListener('resize', setIdeSize)
  });
</script>

<style scoped>
#ide {
  height: 100%;
  position:absolute;
  top:0;
  left:0;
  right:0;
  bottom:0;
}
</style>
