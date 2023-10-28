<template>
  <Navbar />
  <div class="landing-section position-relative w-100 d-flex justify-content-center align-items-center">
    <!-- 
    <div >
      <img src="@/assets/logo.png" alt="logo" /> 
    </div>
    -->
    <div class="rotating-text">
      <p class="me-1">Nos services sont 
      </p>
      <p>
      <span class="word w-1" ref="word1">Diagnostic.</span>
      <span class="word w-2" ref="word2">Etudes.</span>
      <span class="word w-3" ref="word3">Chantier.</span>
      </p>
 
    </div>
  </div>
</template>
<script>
import Navbar from '@/components/Navbar.vue'

export default {
  name: 'landingSection',
  components: { Navbar },
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


<style scoped>
/* Landing */
.landing-section{
  height: calc(100vh - 200px);
  overflow: hidden;
  background: url(@/assets/newYork1.jpg);
  background-size: cover;
}
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

/* Rotator text */
.rotating-text {
  font-family: sans-serif;
  font-weight: 600;
  font-size: 50px;
  color: white;
  transform: translateX(-80px);
}
.rotating-text p {
  display: inline-flex;
  margin: 0;
  vertical-align: top;
}
.rotating-text p .word {
  position: absolute;
  display: flex;
  opacity: 0;
}
.word {
  opacity: 0;
  transition: opacity 0.5s;
}

.word.active {
  opacity: 1;
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

.w-1 {
  color: #e74c3c;
}

.w-2 {
  color: #0f9c22;
}

.w-3 {
  color: #f0690f;
}

</style>