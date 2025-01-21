<script setup lang="ts">
import { onMounted, useTemplateRef } from "vue"
import { EditorView } from "@codemirror/view";
import { basicSetup } from "./codemirror";

const elm = useTemplateRef('container')
const editorDoc = `<template>
  <h1>CodeMirror Editor</h1>
  <div ref="container" class="editor"></div>
</template>`

onMounted(() => {
  new EditorView({
    parent: elm.value as HTMLElement,
    doc: editorDoc,
    extensions: [basicSetup]
  })
})

</script>

<template>
  <h1>CodeMirror Editor</h1>
  <div ref="container" class="editor"></div>
</template>