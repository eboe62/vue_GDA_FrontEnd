<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-toolbar-title>
          {{ appTitle }}
        </q-toolbar-title>
        <div>Release {{ appVersion }}</div>
      </q-toolbar>
    </q-header>
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        >
        </EssentialLink>
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from './App.vue';

export default {
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  data() {
    return {
      appTitle: 'Project Name',
      appVersion: 'v0.1',
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Search',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev',
          level: 0,
          children: [
            {
              title: 'Documents',
              caption: 'quasar.dev',
              icon: 'school',
              link: 'https://quasar.dev',
              level: 1,
              children: [
                {
                  title: 'Search (level 3)',
                  caption: 'quasar.dev',
                  icon: 'school',
                  link: 'https://quasar.dev',
                  level: 2,
                  children: [],
                },
              ],
            },
          ],
        },
        {
          title: 'Github',
          caption: 'github.com/quasarframework',
          icon: 'code',
          link: 'https://github.com/quasarframework',
          level: 0,
          children: [
            {
              title: 'Github Level 2',
              caption: 'quasar.dev',
              icon: 'school',
              link: 'https://quasar.dev',
              level: 1,
              children: [],
            },
          ],
        },
        {
          title: 'Forum',
          caption: 'forum.quasar.dev',
          icon: 'record_voice_over',
          link: 'https://forum.quasar.dev',
          level: 0,
          children: [
            {
              title: 'Forum Level 2',
              caption: 'quasar.dev',
              icon: 'school',
              link: 'https://quasar.dev',
              level: 1,
              children: [],
            },
          ],
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
