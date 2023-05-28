<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <q-page class="flex flex-center bg-grey-2">
        <q-card class="q-pa-md shadow-2 my_card" bordered>
          <q-card-section class="text-center">
            <div class="text-grey-9 text-h5 text-weight-bold">Sign in</div>
            <div class="text-grey-8">Sign in below to access your account</div>
          </q-card-section>
          <q-card-section>
            <q-input
              dense
              outlined
              v-model="localEmail"
              @input="updateEmail"
              label="Email Address"
            ></q-input>
            <q-input
              dense
              outlined
              class="q-mt-md"
              v-model="localPassword"
              @input="updatePassword"
              type="password"
              label="Password"
            ></q-input>
          </q-card-section>
          <q-card-section>
            <q-btn
              style="border-radius: 8px"
              color="dark"
              rounded
              size="md"
              label="Sign in"
              no-caps
              class="full-width"
              @click="goToExampleComponent"
            ></q-btn>
          </q-card-section>
          <q-card-section class="text-center q-pt-none">
            <div class="text-grey-8">
              Don't have an account yet?
              <a
                href="#"
                class="text-dark text-weight-bold"
                style="text-decoration: none"
                >Sign up.</a
              >
            </div>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useRouter } from 'vue-router';

export default defineComponent({
  name: 'LoginComponent',
  props: {
    email: {
      type: String,
      required: true,
    },
    password: {
      type: String,
      required: true,
    },
  },
  computed: {
    localEmail: {
      get() {
        return this.email;
      },
      set(value: string) {
        // Perform any necessary validation or modifications
        // before updating the prop
        this.$emit('update:email', value);
      },
    },
    localPassword: {
      get() {
        return this.email;
      },
      set(value: string) {
        // Perform any necessary validation or modifications
        // before updating the prop
        this.$emit('update:email', value);
      },
    },
  },
  methods: {
    updateEmail(value: string) {
      // Update the localEmail computed property
      this.localEmail = value;
    },
    updatePassword(value: string) {
      // Update the localEmail computed property
      this.localPassword = value;
    },
  },
  setup() {
    // Get the router instance
    const router = useRouter();

    // Define the method to navigate to the About page
    const goToExampleComponent = () => {
      router.push('/example');
    };
    return {
      goToExampleComponent,
    };
  },
});
</script>
