<script lang="ts">
import { defineComponent } from 'vue';
import WebsiteHeader from './components/Header.vue'
import WebsiteFooter from './components/Footer.vue';
import LoginForm from './components/LoginForm.vue';

/**
 * App component. You are welcome to modify this file.
 */
export default defineComponent({
  components: {
    WebsiteHeader,
    WebsiteFooter,
    LoginForm
  },
  data() {
    return {};
  },
});
</script>

<template>
  <WebsiteHeader change-text='Vue is Mega Fun' />
  <main>
    <!-- <div class='home-body'>
      <h2>
        Welcome brave soul... to the world of Vue.js
      </h2>
      <p>
        In this challenge, you will need to implement a simple login page. I have full
        confidence that you'll be able to succeed in this task and look forward to seeing your submission.
      </p>
      <h3>
        Link to challenge:
        <a
          href='https://github.com/Darianlmj/projects-frontend-assessment'
          target='_blank'
        >
          projects-frontend-assessment
        </a>
      </h3>
    </div> -->
    <LoginForm />
  </main>
  <WebsiteFooter />
</template>

<style scoped>
  main {
    padding: 0rem 3rem;
  }

  p {
    font-size: 1.2rem;
  }

  .home-body {
    height: calc(50vh);
    padding: 2rem;
    border-radius: 0.5rem;
    background-color: #f5f5f5;
  }
</style>
