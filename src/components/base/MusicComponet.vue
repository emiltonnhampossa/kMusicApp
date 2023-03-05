<template>



  <q-item clickable v-ripple>
  <q-item side>
    <div class="">


    </div>
    </q-item>
    <q-item-section>
      {{music.title}}
    </q-item-section>
    <q-item-section avatar>
      <q-avatar>
        <img src="https://cdn.quasar.dev/img/boy-avatar.png">
      </q-avatar>
    </q-item-section>
  </q-item>
<div class="q-bg-dark">
  <audio controls autoplay >
  <source :src="music.fileUrl" type="audio/mpeg">
</audio>
</div>






  </template>

  <script>
  import {ref} from 'vue'



  export default{
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
