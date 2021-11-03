<template>
  <input type="text" v-model="model" />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({})
export default class MessageInput extends Vue {
  model!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
