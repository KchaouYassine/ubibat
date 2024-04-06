<template>
  <div class="landing-section position-relative w-100 d-flex justify-content-center align-items-center flex-wrap">
    <div class="w-100" >
      <img src="@/assets/logo.png" alt="logo" /> 
    </div>    
    <div class="rotating-text fw-bold text-white">
      <p class="d-inline-flex m-0 me-3">Nos services sont </p>
      <p class="d-inline-flex m-0 ">
        <span class="word text-red" ref="word1">Diagnostic.</span>
        <span class="word text-green" ref="word2">Etudes.</span>
        <span class="word text-orange" ref="word3">Chantier.</span>
      </p>
    </div>
  </div>
</template>
<script>

export default {
  name: 'landingSection',
  data() {
    return {
      currentWordIndex: 0,
      words: [],
    };
  },
  mounted() {
    this.words = [
      this.$refs.word1,
      this.$refs.word2,
      this.$refs.word3,
    ];
    this.currentWord = this.words[this.currentWordIndex];
    this.currentWord.style.opacity = '1';
    setInterval(this.rotateText, 4000);
  },
  methods: {
    rotateText() {
      this.currentWord.style.opacity = '0';
      this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
      this.currentWord = this.words[this.currentWordIndex];
      this.currentWord.style.opacity = '1';

      this.rotateOutLetters(this.previousWord);
      setTimeout(() => {
        this.rotateInLetters(this.currentWord);
      }, 320);
    },
    rotateOutLetters(word) {
      const letters = word.querySelectorAll('.letter');
      letters.forEach((letter, i) => {
        setTimeout(() => {
          letter.classList.add('out');
        }, i * 80);
      });
    },
    rotateInLetters(word) {
      const letters = word.querySelectorAll('.letter');
      letters.forEach((letter, i) => {
        letter.classList.add('behind');
        setTimeout(() => {
          letter.classList.remove('behind');
          letter.classList.add('in');
        }, 340 + i * 80);
      });
    },
  },
  computed: {
    previousWord() {
      const index = this.currentWordIndex === 0 ? this.words.length - 1 : this.currentWordIndex - 1;
      return this.words[index];
    },
  },

}
</script>


<style lang="scss">
.landing-section{
  height: calc(100vh - 200px);
  overflow: hidden;
  background: url(@/assets/paris.webp);
  background-size: cover

}
.landing-section:before{
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(3, 17, 54, .5) !important ;
}
/*
.landing-section:before{
  content: '';
  position: absolute;
  top: 100%;
  left: -50%;
  width: 100%;
  height: 100%;
  background: #fff;
  transform-origin:right;
  transform: skewY(8deg);
}
.landing-section:after{
  content: '';
  position: absolute;
  top: 100%;
  right: -50%;
  width: 100%;
  height: 100%;
  background: #fff;
  transform-origin:left;
  transform: skewY(-8deg);
}
*/

.rotating-text { 
  font-size: 80px;
  transform: translateX(-80px);
  margin-top: -20%;
  p{
    vertical-align: top;
    .word {
      position: absolute;
      display: flex;
      opacity: 0;
      transition: opacity 0.5s;
    }
    &.active{
      opacity: 1;
    }
  }

}

.rotating-text p .word .letter {
  transform-origin: center center 25px;
}
.rotating-text p .word .letter.out {
  transform: rotateX(90deg);
  transition: 0.32s cubic-bezier(0.6, 0, 0.7, 0.2);
}
.rotating-text p .word .letter.in {
  transition: 0.38s ease;
}
.rotating-text p .word .letter.behind {
  transform: rotateX(-90deg);
}

</style>