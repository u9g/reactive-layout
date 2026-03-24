<template>
  <div class="explorer">
    <div class="section-header">PROJECT</div>
    <div class="tree">
      <div class="tree-item"><span class="icon">📁</span> src</div>
      <div class="tree-item indent"><span class="icon">📄</span> App.vue</div>
      <div class="tree-item indent"><span class="icon">📄</span> main.ts</div>
      <div class="tree-item indent"><span class="icon">📁</span> panels</div>
      <div class="tree-item indent2"><span class="icon">📄</span> Explorer.vue</div>
      <div class="tree-item indent2"><span class="icon">📄</span> Editor.vue</div>
      <div class="tree-item indent2"><span class="icon">📄</span> Terminal.vue</div>
      <div class="tree-item"><span class="icon">📄</span> index.html</div>
      <div class="tree-item"><span class="icon">📄</span> package.json</div>
      <div class="tree-item"><span class="icon">📄</span> vite.config.ts</div>
    </div>
  </div>
</template>

<style scoped>
.explorer { padding: 8px 12px; font-size: 13px; height: 100%; overflow-y: auto; background: #1a1a1a; }
.section-header { font-size: 11px; font-weight: 600; color: #888; letter-spacing: 0.5px; margin-bottom: 8px; }
.tree-item { padding: 3px 4px; border-radius: 3px; cursor: pointer; display: flex; align-items: center; gap: 4px; }
.tree-item:hover { background: #2a2a2a; }
.indent { padding-left: 20px; }
.indent2 { padding-left: 36px; }
.icon { font-size: 14px; width: 18px; text-align: center; }
</style>
