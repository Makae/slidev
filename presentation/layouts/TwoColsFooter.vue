<script setup>
</script>
<style scoped>
    .custom-style {
      background-color: #f3f4f6;
      padding: 2rem;
      border-radius: 8px;
      border-color: black;
      border-style: dotted;
      border-width: 4px;
      display:flex;
      gap: 1rem;
      width: 100%;
      justify-content: center;
      *> {
        width: 50%;
        border: 1px solid green;

      }
    }
  </style>
<template>

  <div class="slidev-layout custom-style">
    <div class="left">
      <slot name="left" />
      <slot name="footer-left" />
    </div>
    <div class="right">
      <slot name="right" />
      <slot name="footer-right" class="footer"/>
    </div>
  </div>
</template>