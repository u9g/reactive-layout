<script setup lang="ts">
import type { PanelTab } from "reactive-layout";

defineProps<{ tab: PanelTab }>();

const icons: Record<string, string> = {
  explorer: '<svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M1.5 1h5l1 2H14.5v11h-13V1zm1 1v10h10V4H7.2L6.2 2H2.5z"/></svg>',
  editor: '<svg width="14" height="14" viewBox="0 0 16 16" fill="#519aba"><path d="M4 2h8a1 1 0 011 1v10a1 1 0 01-1 1H4a1 1 0 01-1-1V3a1 1 0 011-1zm1 2v2h6V4H5zm0 3v1h6V7H5zm0 2v1h4V9H5z"/></svg>',
  terminal: '<svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M2 3h12a1 1 0 011 1v8a1 1 0 01-1 1H2a1 1 0 01-1-1V4a1 1 0 011-1zm1 2v6h10V5H3zm1 1l2 2-2 2v-1l1-1-1-1V6zm4 3h3v1H8V9z"/></svg>',
  preview: '<svg width="14" height="14" viewBox="0 0 16 16" fill="currentColor"><path d="M2 2h12v12H2V2zm1 1v10h10V3H3zm2 2h6v1H5V5zm0 2h6v1H5V7zm0 2h4v1H5V9z"/></svg>',
};
</script>

<template>
  <span style="display:flex;align-items:center;margin-right:5px;opacity:0.85" v-html="icons[tab.panelType] ?? ''"></span>
</template>
