<template>
  <div class="col-8 offset-md-4 my-3">
    <h2>
      {{ base }} <span>{{ displayText.join("") }}</span>
    </h2>
  </div>
</template>

<script>
export default {
  name: "text-animation",
  props: {},
  data() {
    return {
      base: "Typewriter is ",
      speed: 800,
      deleteSpeed: 166,
      displayText: [],
      currentWord: "",
      wordList: ["babboon", "boardgamer", "bard"],
      wordIndex: 0,
    };
  },
  computed: {
    TYPE_SPEED() {
      return this.speed;
    },
    DELETE_SPEED() {
      return this.deleteSpeed;
    },
    timeoutSpeed() {
      return this.TYPE_SPEED * 0.8;
    },
  },
  methods: {
    start() {
      if (this.wordList && this.wordList.length > 0) {
        this.currentWord = this.wordList[this.wordIndex].split("");
        this.wordIndex++;
        this.animate = setTimeout(this.type, this.timeoutSpeed);
      }
    },
    type(word) {
      if (this.currentWord.length > 0) {
        this.displayText.push(this.currentWord.shift());
        // delete when done
      } else if (this.currentWord.length === 0 && this.displayText.length > 0) {
        this.timeoutSpeed = this.DELETE_SPEED;
        this.displayText.pop();
        // done when deleted
      } else if (
        this.currentWord.length === 0 &&
        this.displayText.length === 0
      ) {
        if (this.wordIndex < this.wordList.length) {
          this.currentWord = this.wordList[this.wordIndex].split("");
          this.wordIndex++;
          this.timeoutSpeed = this.TYPE_SPEED;
          this.displayText.push(this.currentWord.shift());
        } else {
          this.wordIndex = 0;
          this.currentWord = this.wordList[this.wordIndex].split("");
          this.displayText.push(this.currentWord.shift());
        }
      }
      setTimeout(this.type, this.timeoutSpeed);
    },
  },
  mounted() {
    this.start();
  },
};
</script>

<style scoped>
.text {
  font-size: 4rem;
}
</style>
