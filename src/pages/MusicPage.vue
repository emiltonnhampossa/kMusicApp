<template>
  <q-page class="q-pa-md text-black">
    <div class="text-grey-8" >
      Lista das Musicas
    </div>
    <q-list class="q-mt-lg">
      <div class="music-list">
    <music-component
      v-for="music in musicsList"
      :music="music"
    />
    
    </div>
    <div>
    <q-btn @click="showForm">Adicionar nova música</q-btn>
    <q-dialog v-model="showingForm">
      <q-card>
        <q-card-section>
          <q-form @submit="addMusic">
            <q-input v-model="title" label="Título" required></q-input>
            <q-input v-model="artist" label="Artista" required></q-input>
            <q-file v-model="audioFile" label="Arquivo de áudio" required></q-file>
            <q-btn type="submit" label="Enviar"></q-btn>
          </q-form>
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
<div>
  
</div>
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
        title:'02.LMS- Presos Injustamente (Feat Maplango)',
        fileUrl:'music-files/02. Presos Injustamente (Feat Maplango).mp3',

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
