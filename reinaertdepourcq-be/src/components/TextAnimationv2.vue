<template>
  <div class="col-8 offset-md-4 my-3">
    <h2>
      {{ base }}<span>{{ displayWord.join("") }}</span>
    </h2>
  </div>
</template>
<script>
export default {
  name: "text-animation-v2",
  props: {},
  data() {
    return {
      base: "Second typewriter is a ",
      wordList: ["test", "failure", "success"],
      displayWord: [],
      currentWord: "",
      activeWord: "",
      wordIndex: 0,
      letterIndex: 0,
      typeSpeed: 450,
      deleteSpeed: 50,
      timeoutSpeed: 9000,
    };
  },
  methods: {
    start() {
      if (this.wordList && this.wordList.length > 0) {
        this.currentWord = this.wordList[this.wordIndex].split("");
        this.activeWord = this.wordList[this.wordIndex].split("");
        this.wordIndex++;
        setTimeout(this.letterLogic, this.typeSpeed);
      }
    },
    removeWord() {
      this.displayWord.pop();
    },
    addWord() {
      this.displayWord.push(this.currentWord.shift());
    },
    letterLogic() {
      if (this.currentWord.length > 0) {
        console.log("add letter");
        setTimeout(this.addWord(), this.typeSpeed);
      } else if (
        this.currentWord.length === 0 &&
        this.displayWord.length === this.activeWord.length
      ) {
        console.log("long wait");
        setTimeout(this.removeWord(), this.timeoutSpeed);
      } else if (this.currentWord.length === 0 && this.displayWord.length > 0) {
        console.log("remove letter");
        setTimeout(this.removeWord(), this.deleteSpeed);
      } else if (
        this.currentWord.length === 0 &&
        this.displayWord.length === 0
      ) {
        if (this.wordIndex < this.wordList.length) {
          console.log("next word");
          this.currentWord = this.wordList[this.wordIndex].split("");
          this.activeWord = this.wordList[this.wordIndex].split("");
          this.wordIndex++;
          this.displayWord.push(this.currentWord.shift());
        } else {
          console.log("reset");
          this.wordIndex = 0;
        }
      }
      setTimeout(this.letterLogic, this.typeSpeed);
    },
  },
  mounted() {
    this.start();
  },
};
</script>
