<script setup lang="ts">
import type { PanelTab } from "reactive-layout";
import ExplorerPanel from "./ExplorerPanel.vue";
import EditorPanel from "./EditorPanel.vue";
import TerminalPanel from "./TerminalPanel.vue";
import PreviewPanel from "./PreviewPanel.vue";

defineProps<{ activeTab: PanelTab }>();
</script>

<template>
  <ExplorerPanel v-if="activeTab.panelType === 'explorer'" />
  <EditorPanel v-else-if="activeTab.panelType === 'editor'" :file="activeTab.label" />
  <TerminalPanel v-else-if="activeTab.panelType === 'terminal'" />
  <PreviewPanel v-else-if="activeTab.panelType === 'preview'" />
</template>
