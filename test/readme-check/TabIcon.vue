<script setup lang="ts">
import type { PanelTab } from "reactive-layout";

defineProps<{ tab: PanelTab }>();
</script>

<template>
  <span class="icon">{{ tab.panelType === 'files' ? '📁' : '📄' }}</span>
</template>
