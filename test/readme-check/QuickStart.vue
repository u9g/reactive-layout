<script setup lang="ts">
import { provide } from "vue";
import { useLayout, SplitLayout } from "reactive-layout";
import MyPanelContent from "./stubs/MyPanelContent.vue";
import MyTabIcon from "./stubs/MyTabIcon.vue";

const { layout, moveTab, removeTab, splitPanel, updateSizesForSplit } = useLayout({
  defaultLayout: {
    type: "split",
    direction: "horizontal",
    sizes: [30, 70],
    children: [
      {
        type: "panel",
        id: "sidebar",
        tabs: [{ id: "files", panelType: "files", label: "Files" }],
        activeTabId: "files",
      },
      {
        type: "panel",
        id: "main",
        tabs: [{ id: "editor", panelType: "editor", label: "Editor" }],
        activeTabId: "editor",
      },
    ],
  },
  storageKey: "my-app-layout",
});

// Required by the layout components
provide("moveTab", moveTab);
provide("closeTab", (tabId: string) => removeTab(tabId));
provide("splitPanel", splitPanel);
provide("updateSizesForSplit", updateSizesForSplit);

// Your app-specific renderers
provide("layoutPanelContent", MyPanelContent);
provide("layoutTabIcon", MyTabIcon);
</script>

<template>
  <SplitLayout :node="layout" />
</template>
