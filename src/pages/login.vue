<template>
 <q-page class="q-pa-md">
    <q-card class="q-pa-md">
      <q-card-section class="q-pb-md">
        <div class="text-h6 q-mb-sm">Login</div>
        <q-input outlined v-model="email" label="E-mail" />
        <q-input outlined v-model="senha" type="password" label="Senha" />
        <q-btn color="primary" label="Entrar" @click="login" class="q-mt-md" />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'login',

  data() {
    return {
      email: '',
      senha: ''
    }
  },
  methods: {
    login() {
      
    }
  }
})
</script>
<style scoped>
</style>