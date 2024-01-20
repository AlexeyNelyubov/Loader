<script setup></script>

<template>
  <div class="loader2"></div>
</template>

<style>
.loader2 {
  width: 50px;
  height: 50px;
  margin-top: 24px;
  border: 5px solid #d9d9d9;
  border-top: 5px solid #60b2ee;
  border-radius: 50%;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
