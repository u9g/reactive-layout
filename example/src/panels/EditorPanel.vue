<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<{ file: string }>();

interface Line { text: string; spans: { cls: string; text: string }[] }

const appLines: Line[] = [
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " { " }, { cls: "fn", text: "provide" }, { cls: "", text: " } " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"vue"' }] },
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " { " }, { cls: "fn", text: "useLayout" }, { cls: "", text: ", " }, { cls: "type", text: "SplitLayout" }, { cls: "", text: " } " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"reactive-layout"' }] },
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " " }, { cls: "type", text: "PanelContent" }, { cls: "", text: " " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"./panels/PanelContent.vue"' }] },
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " " }, { cls: "type", text: "TabIcon" }, { cls: "", text: " " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"./panels/TabIcon.vue"' }] },
  { text: "", spans: [] },
  { text: "", spans: [{ cls: "kw", text: "const" }, { cls: "", text: " { " }, { cls: "var", text: "layout" }, { cls: "", text: ", " }, { cls: "var", text: "moveTab" }, { cls: "", text: ", " }, { cls: "var", text: "splitPanel" }, { cls: "", text: "," }] },
  { text: "", spans: [{ cls: "", text: "  " }, { cls: "var", text: "removeTab" }, { cls: "", text: ", " }, { cls: "var", text: "updateSizesForSplit" }, { cls: "", text: " } = " }, { cls: "fn", text: "useLayout" }, { cls: "", text: "({" }] },
  { text: "", spans: [{ cls: "", text: "  " }, { cls: "prop", text: "defaultLayout" }, { cls: "", text: ": {" }] },
  { text: "", spans: [{ cls: "", text: "    " }, { cls: "prop", text: "type" }, { cls: "", text: ": " }, { cls: "str", text: '"split"' }, { cls: "", text: "," }] },
  { text: "", spans: [{ cls: "", text: "    " }, { cls: "prop", text: "direction" }, { cls: "", text: ": " }, { cls: "str", text: '"horizontal"' }, { cls: "", text: "," }] },
  { text: "", spans: [{ cls: "", text: "    " }, { cls: "prop", text: "sizes" }, { cls: "", text: ": [" }, { cls: "num", text: "25" }, { cls: "", text: ", " }, { cls: "num", text: "75" }, { cls: "", text: "]," }] },
  { text: "", spans: [{ cls: "", text: "    " }, { cls: "prop", text: "children" }, { cls: "", text: ": [" }, { cls: "comment", text: "/* ... */" }, { cls: "", text: "]" }] },
  { text: "", spans: [{ cls: "", text: "  }," }] },
  { text: "", spans: [{ cls: "", text: "  " }, { cls: "prop", text: "storageKey" }, { cls: "", text: ": " }, { cls: "str", text: '"example-layout"' }, { cls: "", text: "," }] },
  { text: "", spans: [{ cls: "", text: "})" }] },
  { text: "", spans: [] },
  { text: "", spans: [{ cls: "fn", text: "provide" }, { cls: "", text: "(" }, { cls: "str", text: '"layoutPanelContent"' }, { cls: "", text: ", " }, { cls: "type", text: "PanelContent" }, { cls: "", text: ")" }] },
  { text: "", spans: [{ cls: "fn", text: "provide" }, { cls: "", text: "(" }, { cls: "str", text: '"layoutTabIcon"' }, { cls: "", text: ", " }, { cls: "type", text: "TabIcon" }, { cls: "", text: ")" }] },
];

const mainLines: Line[] = [
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " { " }, { cls: "fn", text: "createApp" }, { cls: "", text: " } " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"vue"' }] },
  { text: "", spans: [{ cls: "kw", text: "import" }, { cls: "", text: " " }, { cls: "type", text: "App" }, { cls: "", text: " " }, { cls: "kw", text: "from" }, { cls: "", text: " " }, { cls: "str", text: '"./App.vue"' }] },
  { text: "", spans: [] },
  { text: "", spans: [{ cls: "fn", text: "createApp" }, { cls: "", text: "(" }, { cls: "type", text: "App" }, { cls: "", text: ")." }, { cls: "fn", text: "mount" }, { cls: "", text: "(" }, { cls: "str", text: '"#app"' }, { cls: "", text: ")" }] },
];

const lines = computed(() => props.file === "main.ts" ? mainLines : appLines);
</script>

<template>
  <div class="editor">
    <div class="line-numbers">
      <div v-for="n in lines.length" :key="n" class="ln">{{ n }}</div>
    </div>
    <div class="code">
      <div v-for="(line, i) in lines" :key="i" class="line">
        <template v-for="(span, j) in line.spans" :key="j">
          <span v-if="span.cls" :class="span.cls">{{ span.text }}</span>
          <template v-else>{{ span.text }}</template>
        </template>
      </div>
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
