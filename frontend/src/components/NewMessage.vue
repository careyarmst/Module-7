<!-- eslint-disable -->

<template>
  <v-flex sm8 offset-sm2>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title>New Message</v-toolbar-title>
      </v-toolbar>
      <v-form>
        <v-container>
          <v-layout>
            <v-flex xs12 md4>
              <v-text-field v-model="messageBody" label="Message" required> </v-text-field>
            </v-flex>
          </v-layout>
        </v-container>
        <v-btn @click="submit">submit</v-btn>
      </v-form>
    </v-card>
  </v-flex>
</template>

<script>
  export default {
    data() {
      return {
        messageBody: '',
      };
    },
    methods: {
      async submit() {
        try {
          this.$store.dispatch('newMessage', this.messageBody);
        } catch (error) {
          console.error(error);
        }
      },
    },
  };
</script>
