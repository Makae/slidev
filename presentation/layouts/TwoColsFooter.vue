<script setup>
</script>
<style scoped>
    .footer-layout {
      display: grid;
      height: 100%;
      grid-template-columns: auto auto;
      grid-template-rows: 90% auto;
      gap: 1rem;
    }
    .footer-layout > .footer > *  {
      margin: 0.75rem;
      box-sizing: border-box;
    }
    .footer-layout > .footer {
      background-color: #857bb4;

    }
    .footer-layout > .footer-right {
      text-align: right;
    }
  </style>
<template>
  <div class="slidev-layout footer-layout">
    <div class="left">
      <slot name="left" />
   </div>
    <div class="right">
      <slot name="right" />
    </div>
    <div class="footer footer-left">
      <slot name="footer-left" />
    </div>
    <div class="footer footer-right">
      <slot name="footer-right"/>
    </div>
  </div>
</template>