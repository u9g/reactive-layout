<script setup lang="ts">
defineProps<{ file: string }>();
</script>

<template>
  <div class="editor">
    <div class="line-numbers">
      <div v-for="n in 18" :key="n" class="ln">{{ n }}</div>
    </div>
    <div class="code">
      <div class="line"><span class="kw">import</span> { <span class="fn">provide</span> } <span class="kw">from</span> <span class="str">"vue"</span></div>
      <div class="line"><span class="kw">import</span> { <span class="fn">useLayout</span>, <span class="type">SplitLayout</span> } <span class="kw">from</span> <span class="str">"reactive-layout"</span></div>
      <div class="line"><span class="kw">import</span> <span class="type">PanelContent</span> <span class="kw">from</span> <span class="str">"./panels/PanelContent.vue"</span></div>
      <div class="line"><span class="kw">import</span> <span class="type">TabIcon</span> <span class="kw">from</span> <span class="str">"./panels/TabIcon.vue"</span></div>
      <div class="line"></div>
      <div class="line"><span class="kw">const</span> { <span class="var">layout</span>, <span class="var">moveTab</span>, <span class="var">splitPanel</span>,</div>
      <div class="line">  <span class="var">removeTab</span>, <span class="var">updateSizesForSplit</span> } = <span class="fn">useLayout</span>({</div>
      <div class="line">  <span class="prop">defaultLayout</span>: {</div>
      <div class="line">    <span class="prop">type</span>: <span class="str">"split"</span>,</div>
      <div class="line">    <span class="prop">direction</span>: <span class="str">"horizontal"</span>,</div>
      <div class="line">    <span class="prop">sizes</span>: [<span class="num">25</span>, <span class="num">75</span>],</div>
      <div class="line">    <span class="prop">children</span>: [<span class="comment">/* ... */</span>]</div>
      <div class="line">  },</div>
      <div class="line">  <span class="prop">storageKey</span>: <span class="str">"example-layout"</span>,</div>
      <div class="line">})</div>
      <div class="line"></div>
      <div class="line"><span class="fn">provide</span>(<span class="str">"layoutPanelContent"</span>, <span class="type">PanelContent</span>)</div>
      <div class="line"><span class="fn">provide</span>(<span class="str">"layoutTabIcon"</span>, <span class="type">TabIcon</span>)</div>
    </div>
  </div>
</template>

<style scoped>
.editor {
  display: flex;
  height: 100%;
  font-family: "SF Mono", "Fira Code", Menlo, Consolas, monospace;
  font-size: 13px;
  line-height: 20px;
  background: #1e1e1e;
  overflow: auto;
}
.line-numbers {
  padding: 12px 0;
  text-align: right;
  color: #555;
  min-width: 40px;
  padding-right: 12px;
  user-select: none;
}
.ln { height: 20px; }
.code { padding: 12px 0 12px 8px; flex: 1; }
.line { height: 20px; white-space: pre; }
.kw { color: #c586c0; }
.fn { color: #dcdcaa; }
.type { color: #4ec9b0; }
.str { color: #ce9178; }
.var { color: #9cdcfe; }
.prop { color: #9cdcfe; }
.num { color: #b5cea8; }
.comment { color: #6a9955; }
</style>
