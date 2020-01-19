<template>
  <v-app>
    <div>
      <v-app-bar
        color="deep-purple accent-4"
        dense
        dark
      >
        <v-toolbar-title>Practice Page</v-toolbar-title>

        <v-spacer></v-spacer>

        <a class="mx-3 white--text">
          프로찾기
        </a>
        <a class="white--text">
          프로되기
        </a>
      </v-app-bar>
    </div>
    <div>
      <router-view/>
    </div>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {

  },

  data: () => ({
    //
  }),
};
</script>
