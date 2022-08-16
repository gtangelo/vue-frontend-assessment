<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent ({
  name: 'WebsiteFooter',
  props: {
    footerText: {
      type: String,
      required: false,
      default: 'Made with love...'
    },
  },
  data() {
    return {};  
  }
});
</script>

<template>
  <div class='footer-container'>
    <span>
      {{ footerText }}
    </span>
  </div>
</template>

<style scoped>
  .footer-container {
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: #e5e5e5;
  }
</style>