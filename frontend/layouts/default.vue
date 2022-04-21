<template>
  <v-app dark>
    <SideNavMenu :drawer="drawer" :items="loggedInItems" />
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title
        style="cursor: pointer"
        @click="$router.push('/todos')"
        v-text="title"
      />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: "todo-app",
      drawer: false,
      fixed: false,
      loggedInItems: [
        {
          icon: "mdi-apps",
          title: "Todo一覧",
          to: "/todos",
        },
        {
          icon: "mdi-apps",
          title: "Todoを追加する",
          to: "/todo",
        },
      ],
    };
  }
};
</script>