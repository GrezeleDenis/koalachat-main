<template>
  <v-dialog v-model="dialog"
  max-width="60%">
    <v-card-title>
      <span class="text-h5">Entrar em uma sala</span>
    </v-card-title>
    <v-card-text>
    <form>
      <v-text-field
        v-model="name"
        label="Seu nome"
        required
      ></v-text-field>
      <v-text-field
        v-model="roomIp"
        label="Endereço da sala (IP:Port)"
        required
      ></v-text-field>
      <v-text-field
        v-model="roomName"
        label="Nome da sala"
        required
      ></v-text-field>
      <v-text-field
        v-model="roomPassword"
        label="Senha da sala (se tiver)"
      ></v-text-field>

      <v-btn
        class="mr-4"
        @click="join()"
        color='green'
      >
        Entrar
      </v-btn>
      <v-btn 
      @click="closeDialog()"
      color='red'>
        Cancelar
      </v-btn>
    </form>
    </v-card-text>
</v-dialog>
</template>

<script>
export default {
    name: 'JoinServer',
    data: () => ({
      message: "Click",
      dialog: false,
      name: "",
      roomIp: null,
      roomName: "",
      roomPassword: "",
    }),

    methods: {
      open() {
        this.dialog = true;
      },

      closeDialog() {
        this.dialog = false;
      },
    }
};
</script>

<style>
  .v-dialog {
    background-color: white;
  }
</style>