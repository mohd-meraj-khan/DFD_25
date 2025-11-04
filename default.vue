<template>
  <div class="slidev-layout default">
    <div class="slide-number">
      Slide @@slidev-number@@
    </div>
    <slot />
  </div>
</template>

<style>
.slide-number {
  position: absolute;
  bottom: 20px;
  right: 20px;
  font-size: 14px;
  color: #666;
}
</style>
