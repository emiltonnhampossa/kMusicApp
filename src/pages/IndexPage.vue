<template>
  <q-page class="flex flex-center">
    <div class="text-h6 text-grey-3">
      <q-btn
      to="/musics"
      label="Ver musicas"
      color="primary"
      rounded
      unelevated
      size="lg"
      />
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
