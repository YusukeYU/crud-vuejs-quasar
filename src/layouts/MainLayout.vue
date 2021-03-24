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
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-toolbar-title>
          Gerenciador de Tarefas
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
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
import EssentialLink from 'components/EssentialLink.vue'
const linksData = [
  {
    title: 'Home',
    caption: 'Página inicial',
    icon: 'home',
    link: '/'
  },
  {
    title: 'Tarefas',
    caption: 'Gerenciamento de tarefas do sistema',
    icon: 'list_alt',
    link: '/tarefas'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
<style>
.q-item__label--caption {
    color: rgba(0, 0, 0, 0.54)!important;
}
.md-theme-default a:not(.md-button) {
  background-color: #fafafa;
  background-color: var(--md-theme-default-background-variant, #fafafa)!important;
  color: rgba(0,0,0,0.87);
  color: var(--md-theme-default-text-primary-on-background-variant, rgba(0,0,0,0.87))!important;
}
a:not(.md-button):hover {
    text-decoration: none;
}
</style>
