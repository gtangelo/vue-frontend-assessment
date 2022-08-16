<script lang="ts">
import { defineComponent } from 'vue'

/**
 * Header component. You are welcome to modify this file although it might break the challenge.
 * Only modify it if you are confident of your abilities =)
 */

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
    height: 50px;
    display: flex;
    justify-content: center;
    text-align: center;
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: #e5e5e5;
  }
</style>