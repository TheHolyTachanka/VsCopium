<template>
  <div class="">
  <codemirror
    v-model="code"
    placeholder="Code goes here..."
    :autofocus="true"
    :indent-with-tab="true"
    :tab-size="2"
    :extensions="extensions"
    @ready="handleReady"
    @change="log('change', $event)"
    @focus="log('focus', $event)"
    @blur="log('blur', $event)"
  />
  </div>
</template>

<script>
  import { defineComponent } from 'vue'
  import { Codemirror } from 'vue-codemirror'
  import { javascript } from '@codemirror/lang-javascript'
  import { python } from '@codemirror/lang-python'
  import { css } from '@codemirror/lang-css'
  import { html } from '@codemirror/lang-html'
  import { cpp } from '@codemirror/lang-cpp'
  import { rust } from '@codemirror/lang-rust'
  import { oneDark } from '@codemirror/theme-one-dark'
  export default defineComponent({
    components: {
      Codemirror
    },
    setup() {
      const code = ref(`console.log('Hello, world!')`)
      const extensions = [javascript(), oneDark, python(), css(), html(), cpp(), rust()]

      // Codemirror EditorView instance ref
      const view = shallowRef()
      const handleReady = (payload) => {
        view.value = payload.view
      }

      // Status is available at all times via Codemirror EditorView
      const getCodemirrorStates = () => {
        const state = view.value.state
        const ranges = state.selection.ranges
        const selected = ranges.reduce((r, range) => r + range.to - range.from, 0)
        const cursor = ranges[0].anchor
        const length = state.doc.length
        const lines = state.doc.lines
        // more state info ...
        // return ...
      }

      return {
        code,
        extensions,
        handleReady,
        log: console.log
      }
    }
  })
</script>

<style scoped>
</style>