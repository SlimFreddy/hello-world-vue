<template>
  <h1>Hello-World-Vue</h1>
  <MessageInput v-model="msg" />
  <p>{{ message }}</p>
  <button v-on:click="addMessageToMessages()">Hinzufügen</button>
  <p v-for="(item, index) in messages" :key="item">
    {{ index + ". " + item }}
    <button v-on:click="removeMessage(index)">x</button>
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

  removeMessage(index: number): void {
    this.messages.splice(index, 1);
  }
}
</script>

<style lang="scss"></style>
