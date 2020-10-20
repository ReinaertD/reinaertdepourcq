<template>
  <div class="col mx-auto my-3">
    <h2>
      {{ base }}<span class="typewriter">{{ displayWord.join("") }}</span>
    </h2>
  </div>
</template>
<script>
export default {
  name: "text-animation-v2",
  props: {},
  data() {
    return {
      base: "This site is ",
      wordList: [
        "hacked and therefore looks like c*ap.",
        "incomplete.",
        "under construction.",
      ],
      displayWord: [],
      currentWord: "",
      activeWord: "",
      wordIndex: 0,
      typeSpeed: 150,
      deleteSpeed: 20,
      timeoutSpeed: 9000,
    };
  },
  methods: {
    start() {
      if (this.wordList && this.wordList.length > 0) {
        this.currentWord = this.wordList[this.wordIndex].split("");
        // this.activeWord = this.wordList[this.wordIndex].split("");
        this.wordIndex++;
        setTimeout(this.wordLogic, this.typeSpeed);
      }
    },
    removeWord() {
      this.displayWord.pop();
    },
    addWord() {
      this.displayWord.push(this.currentWord.shift());
    },
    wordLogic() {
      // console.log("Start");
      if (this.currentWord.length === 1) {
        // console.log("Add");
        setTimeout(this.addWord(), this.typeSpeed);
        setTimeout(this.wordLogic, this.typeSpeed + 2000);
      } else if (this.currentWord.length > 0) {
        // console.log("Add");
        setTimeout(this.addWord(), this.typeSpeed);
        setTimeout(this.wordLogic, this.typeSpeed);
      } else if (this.currentWord.length === 0 && this.displayWord.length > 0) {
        setTimeout(this.removeWord(), this.deleteSpeed);
        setTimeout(this.wordLogic, this.typeSpeed);
        // console.log("Remove");
      } else if (
        this.currentWord.length === 0 &&
        this.displayWord.length === 0
      ) {
        // console.log("New word");
        if (this.wordIndex < this.wordList.length) {
          // console.log("Next word");
          this.currentWord = this.wordList[this.wordIndex].split("");
          this.wordIndex++;
          this.displayWord.push(this.currentWord.shift());
          setTimeout(this.wordLogic, this.typeSpeed);
        } else {
          // console.log("Reset");
          this.wordIndex = 0;
          setTimeout(this.wordLogic, this.typeSpeed);
        }
      }
    },
  },
  mounted() {
    this.start();
  },
};
</script>

<style scoped>
.typewriter {
  border-right: 0.1em solid black;
  animation: blink-caret 0.75s step-end infinite;
}
h2 {
  text-align: center;
}
@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: black;
  }
}
</style>
