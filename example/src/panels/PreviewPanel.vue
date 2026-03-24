<template>
  <div class="preview">
    <div class="card">
      <h2>reactive-layout</h2>
      <p>Split panes, draggable tabs, and resizable panels — all built with Vue 3.</p>
      <div class="features">
        <div class="feature">
          <span class="check">✓</span> Drag tabs between panels
        </div>
        <div class="feature">
          <span class="check">✓</span> Drop on edges to split
        </div>
        <div class="feature">
          <span class="check">✓</span> Resize panes by dragging
        </div>
        <div class="feature">
          <span class="check">✓</span> Persistent layout via localStorage
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.preview {
  padding: 24px;
  height: 100%;
  background: #1a1a1a;
  display: flex;
  align-items: flex-start;
  justify-content: center;
}
.card {
  background: #252526;
  border: 1px solid #333;
  border-radius: 8px;
  padding: 24px 28px;
  max-width: 360px;
}
h2 {
  font-size: 18px;
  font-weight: 600;
  color: #f5f5f5;
  margin-bottom: 8px;
}
p {
  font-size: 13px;
  color: #999;
  line-height: 1.5;
  margin-bottom: 16px;
}
.features { display: flex; flex-direction: column; gap: 6px; }
.feature { font-size: 13px; color: #ccc; display: flex; align-items: center; gap: 8px; }
.check { color: #00b8a3; font-weight: bold; }
</style>
