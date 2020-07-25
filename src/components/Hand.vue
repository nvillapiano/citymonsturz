<template>
  <div class="hand-unit" :class="right ? 'right' : 'left'">
    <nav class="hand-tools">
      <h1 v-if="right" class='hand-title'>Right hand</h1>
      <h1 v-else class='hand-title'>Left hand</h1>
      <!-- left -->
      <div v-if="left" @click="changeLeftHand($event)" class='hand-list left'>
        <div v-for='lefthand in leftHands' :key='lefthand' class='hand-thumb'>
          <img data-cat="left" :data-hand="`${lefthand}`" class="hand-thumb-img" :src="`/assets/hands/left/type 0${lefthand}.svg`">
        </div>
      </div>
      <!-- right -->
      <div v-if="right" @click="changeRightHand($event)" class='hand-list right'>
        <div v-for='righthand in rightHands' :key='righthand' class='hand-thumb'>
          <img data-cat="right" :data-hand="`${righthand}`" class="hand-thumb-img" :src="`/assets/hands/right/type 0${righthand}.svg`">
        </div>
      </div>

    </nav>
    <div v-if="left" class="hand hand-left"></div>
    <div v-if="right" class="hand hand-right"></div>
  </div>
</template>

<script>
export default {
  name: 'Hand',
  props: {
    left: Boolean,
    right: Boolean
  },
  data () {
    return {
      leftHands: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      rightHands: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ]
    }
  },
  methods: {
    changeLeftHand: function(event) {
      const handID = event.target.dataset.hand;
      const handCat = event.target.dataset.cat;
      const handLeft = document.getElementsByClassName('hand-left')[0];
      handLeft.style.backgroundImage = `url('/assets/hands/${handCat}/type 0${handID}.svg')`;
      console.log('left', handID, handCat, handLeft)
    },
    changeRightHand: function(event) {
      const handID = event.target.dataset.hand;
      const handCat = event.target.dataset.cat;
      const handRight = document.getElementsByClassName('hand-right')[0];
      handRight.style.backgroundImage = `url('/assets/hands/${handCat}/type 0${handID}.svg')`;
      console.log('right', handID, handCat, handRight)
    },
  }
}
</script>


<style lang="scss">

  .hand-unit {

    &.left {

      .hand-tools {
        top: calc(50vh + 2rem);
        height: 20rem;
      }
    }

    &.right {

      .hand-tools {
        top: 3  * 25vh;
      }
    }
  }

  .hand {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    background: center center no-repeat;
    background-size: contain;
    //
    background-image: url('/assets/hands/left/type 01.svg');
    width: 24rem;
    height: 24rem;
    //
    bottom: 0;
    margin: 0 0 0 -10vw;

    &.hand-right {
      margin: 0 -0.4vw 0 14vw;
    }
  }


</style>
