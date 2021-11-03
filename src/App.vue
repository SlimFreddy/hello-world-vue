<template>
  <h1>Hello-World-Vue</h1>
  <MessageInput v-model="msg" />
  <p>{{ message }}</p>
  <button v-on:click="addMessageToMessages()">Hinzufügen</button>
  <p v-for="item in messages" :key="item">
    {{ item }}
  </p>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import MessageInput from "./components/MessageInput.vue";
@Options({
  components: {
    MessageInput,
  },
})
export default class App extends Vue {
  private msg = "";
  messages: string[] = [];

  get message(): string {
    return "Nachricht: " + this.msg;
  }

  addMessageToMessages(): void {
    this.messages.push(this.msg);
  }
}
</script>

<style lang="scss"></style>
