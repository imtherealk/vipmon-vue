<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        argon
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-content>
      <VipToptalkers/>
    </v-content>
  </v-app>
</template>

<script>
import VipToptalkers from './components/VipToptalkers.vue';

export default {
  name: 'App',

  components: {
    VipToptalkers,
  },

  data: () => ({
    //
  }),
};
</script>