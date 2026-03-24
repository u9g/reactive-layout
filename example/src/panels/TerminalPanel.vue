<template>
  <div class="terminal">
    <div class="line"><span class="prompt">~/project $</span> npm run dev</div>
    <div class="line output"></div>
    <div class="line output">  <span class="vite">VITE</span> v8.0.1  ready in 142 ms</div>
    <div class="line output"></div>
    <div class="line output">  ➜  Local:   <span class="url">http://localhost:5173/</span></div>
    <div class="line output">  ➜  Network: use --host to expose</div>
    <div class="line output"></div>
    <div class="line"><span class="cursor">█</span></div>
  </div>
</template>

<style scoped>
.terminal {
  padding: 12px;
  font-family: "SF Mono", "Fira Code", Menlo, Consolas, monospace;
  font-size: 13px;
  line-height: 20px;
  background: #0e0e0e;
  height: 100%;
  overflow-y: auto;
  color: #d4d4d4;
}
.prompt { color: #6a9955; }
.vite { color: #a78bfa; font-weight: bold; }
.url { color: #569cd6; }
.output { color: #ccc; }
.cursor { color: #d4d4d4; animation: blink 1s step-end infinite; }
@keyframes blink { 50% { opacity: 0; } }
</style>
