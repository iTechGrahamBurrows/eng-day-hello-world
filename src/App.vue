<script setup>
import * as Tone from 'tone';

const letterH = 'h.mp3';
const letterE = 'e.mp3';
const letterL = 'l.mp3';
const letterO = 'o.mp3';
const letterW = 'w.mp3';
const letterR = 'r.mp3';
const letterD = 'd.mp3';
let playerH = new Tone.Player(letterH).toDestination();
let playerE = new Tone.Player(letterE).toDestination();
let playerL = new Tone.Player(letterL).toDestination();
let playerO = new Tone.Player(letterO).toDestination();
let playerW = new Tone.Player(letterW).toDestination();
let playerR = new Tone.Player(letterR).toDestination();
let playerD = new Tone.Player(letterD).toDestination();

addEventListener('keydown', (event) => {
  Tone.loaded().then(() => {
    switch (event.keyCode) {
      case 72:
        playerH.start();

        break
      case 69:
        playerE.start();
        break
      case 76:
        playerL.start();
        break
      case 79:
        playerO.start();
        break
      case 87:
        playerW.start();
        break
      case 82:
        playerR.start();
        break
      case 68:
        playerD.start();
        break
    }
  });
});

function makeFontLarge () {

}

</script>

<template>
  <main>
    type <span class="letter-h" :class="[{'large-font': makeFontLarge('h')}]">h</span>ello world
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

main span {
  transition: all .2s ease
}

.large-font {
  font-size: 100px
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
