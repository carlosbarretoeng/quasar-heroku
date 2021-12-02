<template>
  <q-page class="flex flex-center">
    <q-card id="card" class="bg-grey-4">
      <q-card-section class="column text-center">
        <img
          alt="Quasar logo"
          src="https://unifagoc.edu.br/download/a/logo-unifagoc-colorido-transparente.png"
          style="width: 100%; height: auto"
        >
        <span class="text-h5 q-my-md">Seja bem vindo ao SIGA</span>

        <div class="q-gutter-sm">
          <q-input outlined label="Usuário" bg-color="white" />
          <q-input outlined type="password" label="Senha" bg-color="white" />
          <q-btn color="primary" label="Acessar" to="/app/"/>
          <br/>
          <q-btn flat color="primary" label="Esqueceu a senha?"/>
          <br/>
          <q-btn-group flat spread>
            <q-btn flat size="sm" class="q-pa-none" label="Política de Privacidade"/>
            <q-btn flat size="sm" class="q-pa-none" label="Termos de Serviço"/>
          </q-btn-group>
        </div>
      </q-card-section>
      <div class="text-caption text-center q-pb-md">
        © 2011 - 2021 Fagoc Tech. Versão 2019.10.4
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageLogin',
});
</script>

<style scoped>
#card{
  width: 320px;
}
</style>
