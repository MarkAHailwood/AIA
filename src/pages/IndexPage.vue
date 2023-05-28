<template>
  <login-component :email="email" :password="password"></login-component>
</template>

<script lang="ts">
//import ExampleComponent from 'components/ExampleComponent.vue';
import LoginComponent from 'src/components/LoginComponent.vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  components: { LoginComponent },
  data() {
    return {
      email: 'example@example.com',
      password: '',
    };
  },
});
</script>
