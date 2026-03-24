<script setup lang="ts">
import { provide } from "vue";
import { useLayout, SplitLayout } from "reactive-layout";
import type { SplitNode } from "reactive-layout";
import PanelContent from "./panels/PanelContent.vue";
import TabIcon from "./panels/TabIcon.vue";

const defaultLayout: SplitNode = {
  type: "split",
  direction: "horizontal",
  sizes: [22, 78],
  children: [
    {
      type: "panel",
      id: "sidebar",
      tabs: [
        { id: "explorer", panelType: "explorer", label: "Explorer" },
      ],
      activeTabId: "explorer",
    },
    {
      type: "split",
      direction: "vertical",
      sizes: [65, 35],
      children: [
        {
          type: "panel",
          id: "editor",
          tabs: [
            { id: "app", panelType: "editor", label: "App.vue" },
            { id: "main", panelType: "editor", label: "main.ts" },
            { id: "preview", panelType: "preview", label: "Preview" },
          ],
          activeTabId: "app",
        },
        {
          type: "panel",
          id: "terminal",
          tabs: [
            { id: "term", panelType: "terminal", label: "Terminal" },
          ],
          activeTabId: "term",
        },
      ],
    },
  ],
};

const { layout, moveTab, removeTab, splitPanel, updateSizesForSplit, resetLayout } =
  useLayout({ defaultLayout, storageKey: "example-layout" });

provide("moveTab", moveTab);
provide("closeTab", (tabId: string) => removeTab(tabId));
provide("splitPanel", splitPanel);
provide("updateSizesForSplit", updateSizesForSplit);
provide("layoutPanelContent", PanelContent);
provide("layoutTabIcon", TabIcon);
</script>

<template>
  <SplitLayout :node="layout" />
</template>
