<template>
  <q-layout view="hHh Lpr lFr">
    <q-header>
      <q-toolbar class="bg-unifagoc-background text-dark">
        <div class="row">
          <h5 class="q-ma-none">
            Quasar App
          </h5>

          <q-btn
            flat
            dense
            round
            icon="menu"
            aria-label="Menu"
            @click="toggleLeftDrawer"
          />
        </div>

        <q-space/>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      class="bg-unifagoc-background"
      v-model="leftDrawerOpen"
      show-if-above
    >
      <q-list>
        <q-item-label header >
          Home
        </q-item-label>

        <EssentialLink
          v-for="link in homeLinksList"
          :key="link.title"
          v-bind="link"
        />
        <q-item-label header >
          Áreas
        </q-item-label>

        <EssentialLink
          v-for="link in areasLinksList"
          :key="link.title"
          v-bind="link"
        />
        <q-item-label header >
          Estatísticas
        </q-item-label>

        <EssentialLink
          v-for="link in estatisticasLinksList"
          :key="link.title"
          v-bind="link"
        />
        <q-item-label header >
          Contatos
        </q-item-label>

        <EssentialLink
          v-for="link in contatosLinksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container id="pageContainer">
      <div>
        <router-view />
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue';

const homeLinksList = [
  {
    title: 'Docs',
    icon: 'school',
    link: 'https://quasar.dev',
  },
];

const areasLinksList = [
  {
    title: 'Docs',
    icon: 'school',
    link: 'https://quasar.dev',
  },
];

const estatisticasLinksList = [
  {
    title: 'Docs',
    icon: 'school',
    link: 'https://quasar.dev',
  },
];

const contatosLinksList = [
  {
    title: 'Docs',
    icon: 'school',
    link: 'https://quasar.dev',
  },
];

import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      homeLinksList,
      areasLinksList,
      estatisticasLinksList,
      contatosLinksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>

<style scoped>
#pageContainer{
  margin-left: 32px;
}

#pageContainer > div{
  background: white;
  border-top-left-radius: 16px;
  border-top-right-radius: 16px;
  width: calc(100% - 32px);
  height: calc(100% - 2px);
}
</style>
