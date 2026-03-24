<script setup lang="ts">
import type { PanelTab } from "reactive-layout";

defineProps<{ activeTab: PanelTab }>();
</script>

<template>
  <div v-if="activeTab.panelType === 'files'">files</div>
  <div v-else-if="activeTab.panelType === 'editor'">editor</div>
  <div v-else-if="activeTab.panelType === 'terminal'">terminal</div>
</template>
