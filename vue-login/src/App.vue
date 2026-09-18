<script setup>
import LoginCard from './components/LoginCard.vue'
</script>

<template>
  <div class="login-page">
    <LoginCard />
  </div>
</template>

<style>
/*
 * 全屏登录背景。
 * 背景图放在 public/ 下（文件名见 url）。若图片缺失，会自动回退到渐变背景，页面依然美观。
 * 想用自己的图：把图片命名为 Honkai_Star_Rail_style_cinemat_2026-09-14T03-42-18.png 放到 public/ 即可。
 */
.login-page {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  color: var(--text);
  background-color: #312e81;
  background-image:
    url("/Honkai_Star_Rail_style_cinemat_2026-09-14T03-42-18.png"),
    linear-gradient(135deg, #4f46e5 0%, #7c3aed 50%, #4c1d95 100%);
  background-repeat: no-repeat, no-repeat;
  background-position: center, center;
  background-size: cover, cover;
  background-attachment: fixed, fixed;
}

/* 暗色遮罩：保证登录卡片在任何背景上都清晰可读 */
.login-page::before {
  content: "";
  position: fixed;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(15, 23, 42, 0.62) 0%,
    rgba(49, 46, 129, 0.55) 50%,
    rgba(76, 29, 149, 0.6) 100%
  );
  z-index: 0;
  pointer-events: none;
}

.login-page > * {
  position: relative;
  z-index: 1;
}
</style>
