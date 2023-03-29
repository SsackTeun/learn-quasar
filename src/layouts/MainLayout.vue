<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Quasar App </q-toolbar-title>

        <q-btn flat round dense :icon="$q.dark.isActive ? 'dark_mode' : 'light_mode'"
        @click="$q.dark.toggle()"
        />
<!--        dark-mode-->
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Quasar v{{ $q.version }} </q-item-label>
          <q-avatar size="lg">
            <img src="logo.png"/>
          </q-avatar>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<script>
const linksList = [
  {
    title: 'Typography',
    caption: 'quasar.dev',
    icon: 'school',
    to: '/typography',
  },
  {
    title: 'Colors',
    caption: 'quasar.dev',
    icon: 'school',
    to: '/colors',
  },
  {
    title: 'Spacing',
    caption: 'quasar.dev',
    icon: 'school',
    to: '/spacing',
  },
  {
    title: 'BreakPoints',
    caption: 'quasar.dev',
    icon: 'school',
    to: '/breakpoints',
  },
  {
    title: 'Classes & variables',
    caption: 'quasar.dev',
    icon: 'school',
    to: '/classes-variables',
  }
];

</script>
<script setup >
import { defineComponent, ref } from 'vue';
import EssentialLink from 'components/EssentialLink.vue';

    const leftDrawerOpen = ref(false);
    const essentialLinks = linksList;
     const toggleLeftDrawer = () => leftDrawerOpen.value = !leftDrawerOpen.value;

</script>
