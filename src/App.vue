<template>
  <div id="app">
    <div class="flex flex-col justify-center items-center">
      <div>Send To The Lion:</div>
      <input
        class="w-64 content-center shadow border rounded px-4 mb-2"
        type="text"
        v-model="speakText"
      />
      <button
        @click="lionText = speakText"
        class="bg-blue-500 text-white py-2 px-2 rounded mb-4"
      >
        Send It!
      </button>
    </div>
    <hr class="my-4" />
    <div class="flex justify-center text-center w-full">
      <!-- <LionSpeak :lionText="lionText" @input="speakText = $event" /> -->
      <!-- <LionSpeak :lionText.sync="lionText" /> -->
      <LionSpeak v-model:lionText="lionText" />
    </div>
  </div>
</template>

<script>
import LionSpeak from "./components/lion-speak";
export default {
  name: "App",
  data: () => ({
    speakText: "Roar",
    lionText: ""
  }),
  components: {
    LionSpeak
  },
  watch: {
    lionText() {
      this.speakText = this.lionText;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
