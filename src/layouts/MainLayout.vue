<template>
 <div>
  <q-fab elevated round icon="color_lens" @click="toggleTheme" 
  class="q-fab--absolute q-fab--bottom q-fab--right"/>
    <q-layout view="lHh Lpr lFf">
      
    <q-header elevated>
        <q-toolbar>

          <q-toolbar-title>emusic-app</q-toolbar-title>

          <q-btn round>
      <q-avatar size="42px">
        <img src="https://cdn.quasar.dev/img/avatar2.jpg">
      </q-avatar>

        <q-menu>
          <q-list style="min-width: 100px">
            <q-item to="/" clickable v-close-popup exact>
              <q-item-section>Inicio</q-item-section>
            </q-item>
            <q-item to="/musics" clickable v-close-popup exact>
              <q-item-section>Musicas</q-item-section>
            </q-item>
            <q-item clickable v-close-popup exact>
              <q-item-section>Musicas BAixadas</q-item-section>
            </q-item>
            <q-separator />
            <q-item to="/login" clickable v-close-popup exact>
              <q-item-section>Login</q-item-section>

            </q-item>
          </q-list>
        </q-menu>
      </q-btn>
        </q-toolbar>
      </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
  </div>

</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },
  methods: {
    toggleTheme() {
      this.$q.dark.toggle();
    }
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
<style>
.q-fab--absolute {
  position: absolute;
}

.q-fab--bottom {
  bottom: 24px;
}

.q-fab--right {
  right: 24px;
}
</style>
