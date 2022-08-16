<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'LoginForm',
  props: {},
  data() {
    return {
      username: '',
      password: '',
      modalMessage: '',
      modalVisible: false,
    };
  },
  methods: {
    async login() {
      const res = await fetch('http://localhost:3000/auth/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          username: this.username,
          password: this.password,
        }),
      });
      const data = await res.json();
      this.modalMessage = data.message;
      this.modalVisible = true;
    },
    toggleModal() {
      this.modalVisible = !this.modalVisible;
    }
  },
});
</script>

<template>
  <div class='flex justify-center mt-12'>
    <form class='bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 w-2/6'>
      <div>
        <label
          class='block'
          for='username'
        >
          Username
        </label>
        <input
          id='username'
          v-model='username'
          class='border rounded my-2 py-2 px-3'
          type='text'
          placeholder='Username'
        >
      </div>
      <div>
        <label
          class='block'
          for='password'
        >
          Password
        </label>
        <input
          id='password'
          v-model='password'
          class='border rounded my-2 py-2 px-3'
          type='password'
          placeholder='Password'
        >
      </div>
      <div class='flex justify-center mt-5'>
        <button
          class='bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded'
          type='button'
          @click='login'
        >
          Login
        </button>
      </div>
    </form>
  </div>
  <div v-if='modalVisible'>
    <div
      class='modal-overlay'
      @click='toggleModal'
    />
    <div class='modal-container'>
      {{ modalMessage }}
    </div>
  </div>
</template>

<style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 100;
  }

  .modal-container {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 1rem;
    border-radius: 0.5rem;
    z-index: 101;
  }
</style>
