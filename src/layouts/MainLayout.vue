<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar class="glossy">
        <q-toolbar-title class="absolute-center">
          Awesome To Do
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-footer>
      <q-tabs>
        <q-route-tab
          v-for="nav in navs"
          :key="nav.label"
          :icon="nav.icon"
          :label="nav.label"
          :to="nav.to"
        />
      </q-tabs>
    </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="bg-primary"
      :breakpoint="767"
      :width="250"
    >
      <q-list dark>
        <q-item-label header>Navigation</q-item-label>
        <q-item
          clickable
          v-for="nav in navs"
          :key="nav.label"
          :to="nav.to"
          class="text-grey-4 text-bold"
          exact
        >
          <q-item-section avatar>
            <q-icon :name="nav.icon" />
          </q-item-section>
          <q-item-section>
            <q-item-label>{{ nav.label }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  data() {
    return {
      navs: [
        {
          label: "To do",
          icon: "list",
          to: "/",
        },
        {
          label: "Settings",
          icon: "settings",
          to: "/settings",
        },
        {
          label: "about",
          icon: "info",
          to: "/about",
        },
      ],
    };
  },
};
</script>

<style>
@media screen and (min-width: 768px) {
  .q-footer {
    display: none;
  }
}
</style>