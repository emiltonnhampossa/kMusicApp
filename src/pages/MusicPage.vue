<template>
  <q-page class="q-pa-md bg-dark text-white">
    <div class="text-h6">
      Lista das Musicas
    </div>
    <q-list bordered class="q-mt-lg">
      <music-component
      v-for="music in musicsList"
      :music="music"
      />



    </q-list>
  </q-page>
</template>

<script>

import { defineComponent, ref } from 'vue'
import MusicComponent  from "components/base/MusicComponet.vue";

export default defineComponent({
  name: 'MusicPage',
  components:{MusicComponent},
  setup (){
    const musicsList = ref([
        { id:'01. Intro (feat Maplango).mp3',
        title:'01.LMS- Intro (feat Maplango)',
        fileUrl:'music-files/01. Intro (feat Maplango).mp3',
      },
        {id:'02. Presos Injustamente (Feat Maplango).mp3',
        title:'02.LMS- Presos Injustamente (Feat Maplango)'

      },
        {
        id:'03. Jorge (Feat Dash).mp3',
        title:'03.LMS- Jorge (Feat Dash)',
        fileUrl:'music-files/03. Jorge (Feat Dash).mp3',
      }

    ])
    return{
      musicsList
    }
  }
})
</script>
