<template>

  <q-list bordered class="q-mt-lg">

    <q-item clickable v-ripple>
    <q-item-section avatar>
      <q-avatar rounded>
        <img src="public/icons/favicon-128x128.png">
      </q-avatar>
    </q-item-section>
    <q-item-section>{{music.title}}</q-item-section>
    <q-item-section side>
        <div>
            <q-btn
            @click="downloadAudio"
            v-if="canStartPlay"
         @click.stop="canStartPlay = false"
         icon="pause"
         round
         flat
         />

         <q-btn
         @click="downloadAudio"
            v-else
         @click.stop="canStartPlay = true"
         icon="play_circle_filled"
         round
         flat
         />
         <q-btn
         @click="downloadAudio"
      icon="file_download"
        round
        flat
         download
         />


         </div>
    </q-item-section>
  </q-item>


</q-list>
<audio
v-if="canStartPlay"
v-show="false"
controls
autoplay
>
<source
:src="music.fileUrl"
type="audio/mpeg">
Your browser does not support the audio element.
</audio>
  </template>

  <script>
  import {ref} from 'vue'

  export default{
    data() {
    return {
      showingForm: false,
      title: '',
      artist: '',
      audioFile: null
    };
  },

    methods: {
    async downloadAudio() {
      const audioUrl ='music-files/01. Intro (feat Maplango).mp3';
      const response = await fetch(audioUrl);
      const blob = await response.blob();
      const objectUrl = URL.createObjectURL(blob);

      const downloadLink = document.createElement('a');
      downloadLink.href = objectUrl;
      downloadLink.download = 'audio.mp3';

      document.body.appendChild(downloadLink);
      downloadLink.click();
      document.body.removeChild(downloadLink);
    }
  },

  
    name: 'MusicComponet',
    props:['music'],
    setup(){

        const canStartPlay = ref(false)

        return{
          canStartPlay
        }
      }
    }
  </script>

  <style scoped>

  </style>
