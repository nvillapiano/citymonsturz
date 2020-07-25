<template>
  <div class="hand-unit" :class="right ? 'right' : 'left'">
    <nav class="hand-tools">
      <div class="hand-trigger" @click="triggerControls()">
        <svg fill="#000000" viewBox="0 0 512 512" x="0px" y="0px">
          <path d="M315.73,512H196.29a26.79,26.79,0,0,1-26.87-26.63v-62a180.91,180.91,0,0,1-15.71-9.09l-53.87,31a26.83,26.83,0,0,1-36.53-9.74L3.6,332.48a26.61,26.61,0,0,1,9.79-36.38l54-31q-0.22-4.55-.22-9.05t0.22-9.05l-54-31a26.58,26.58,0,0,1-9.79-36.38l59.71-103a26.81,26.81,0,0,1,36.5-9.75l53.9,31a181.34,181.34,0,0,1,15.71-9.09v-62A26.78,26.78,0,0,1,196.29,0H315.73A26.78,26.78,0,0,1,342.6,26.63v62a180.91,180.91,0,0,1,15.71,9.09l53.87-31a26.83,26.83,0,0,1,36.53,9.74l59.72,103a26.61,26.61,0,0,1-9.79,36.38l-54,31q0.22,4.55.22,9.05t-0.22,9.05l54,31a26.61,26.61,0,0,1,9.79,36.38l-59.71,103a26.81,26.81,0,0,1-36.5,9.75l-53.9-31a181.34,181.34,0,0,1-15.71,9.09v62A26.79,26.79,0,0,1,315.73,512ZM206.66,474.9h98.69V399.36l11.28-4.82A145.87,145.87,0,0,0,346.3,377.4l9.82-7.26,65.6,37.75L470.92,323l-65.64-37.75,1.37-12.07a150.8,150.8,0,0,0,0-34.35l-1.37-12.07L470.91,189l-49.2-84.9-65.58,37.76-9.82-7.26a145.87,145.87,0,0,0-29.66-17.14l-11.28-4.82V37.1H206.66v75.54l-11.28,4.82a145.87,145.87,0,0,0-29.66,17.14l-9.82,7.26-65.6-37.75L41.1,189l65.64,37.75-1.37,12.07a150.87,150.87,0,0,0,0,34.35l1.37,12.07L41.11,323l49.2,84.9,65.58-37.76,9.82,7.26a145.87,145.87,0,0,0,29.66,17.14l11.28,4.82V474.9ZM480,328.23h0ZM256,344.12c-48.77,0-88.45-39.53-88.45-88.12s39.68-88.12,88.45-88.12,88.45,39.53,88.45,88.12S304.78,344.12,256,344.12ZM256,205a51,51,0,1,0,51.21,51A51.17,51.17,0,0,0,256,205Z"></path>
          <path d="M256,344.12c-48.77,0-88.45-39.53-88.45-88.12s39.68-88.12,88.45-88.12,88.45,39.53,88.45,88.12S304.77,344.12,256,344.12ZM256,205a51,51,0,1,0,51.21,51A51.17,51.17,0,0,0,256,205Z"></path>
        </svg>
      </div>
      <h1 v-if="right" class='hand-title'>Right hand</h1>
      <h1 v-else class='hand-title'>Left hand</h1>
      <div class="hand-panel">
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

        <div class="hand-controls" :class="toggleHand ? 'show' : ''">
          <div class="control size">
            <div class="icon size">
              <svg fill="#000000" viewBox="0 0 100 100" x="0px" y="0px">
                <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                  <g fill="#000000">
                    <path d="M53.5286188,50.7001917 C53.1419136,50.3134865 53.1478061,49.680621 53.5286188,49.2998083 L62.7998083,40.0286188 C63.1865135,39.6419136 63.5,39.7693525 63.5,40.3255584 L63.5,42.5005349 C63.5,43.604809 64.3877296,44.5 65.5,44.5 L65.5,44.5 C66.6045695,44.5 67.5,43.5980496 67.5,42.4914698 L67.5,34.5085302 C67.5,33.3992496 66.5980496,32.5 65.4914698,32.5 L57.5085302,32.5 C56.3992496,32.5 55.5,33.3877296 55.5,34.5 L55.5,34.5 C55.5,35.6045695 56.4008192,36.5 57.4994651,36.5 L59.6744416,36.5 C60.225142,36.5 60.3521939,36.819379 59.9713812,37.2001917 L50.7001917,46.4713812 C50.3134865,46.8580864 49.680621,46.8521939 49.2998083,46.4713812 L40.0286188,37.2001917 C39.6419136,36.8134865 39.7693525,36.5 40.3255584,36.5 L42.5005349,36.5 C43.604809,36.5 44.5,35.6122704 44.5,34.5 L44.5,34.5 C44.5,33.3954305 43.5980496,32.5 42.4914698,32.5 L34.5085302,32.5 C33.3992496,32.5 32.5,33.4019504 32.5,34.5085302 L32.5,42.4914698 C32.5,43.6007504 33.3877296,44.5 34.5,44.5 L34.5,44.5 C35.6045695,44.5 36.5,43.5991808 36.5,42.5005349 L36.5,40.3255584 C36.5,39.774858 36.819379,39.6478061 37.2001917,40.0286188 L46.4713812,49.2998083 C46.8580864,49.6865135 46.8521939,50.319379 46.4713812,50.7001917 L37.2001917,59.9713812 C36.8134865,60.3580864 36.5,60.2306475 36.5,59.6744416 L36.5,57.4994651 C36.5,56.395191 35.6122704,55.5 34.5,55.5 L34.5,55.5 C33.3954305,55.5 32.5,56.4019504 32.5,57.5085302 L32.5,65.4914698 C32.5,66.6007504 33.4019504,67.5 34.5085302,67.5 L42.4914698,67.5 C43.6007504,67.5 44.5,66.6122704 44.5,65.5 L44.5,65.5 C44.5,64.3954305 43.5991808,63.5 42.5005349,63.5 L40.3255584,63.5 C39.774858,63.5 39.6478061,63.180621 40.0286188,62.7998083 L49.2998083,53.5286188 C49.6865135,53.1419136 50.319379,53.1478061 50.7001917,53.5286188 L59.9713812,62.7998083 C60.3580864,63.1865135 60.2306475,63.5 59.6744416,63.5 L57.4994651,63.5 C56.395191,63.5 55.5,64.3877296 55.5,65.5 L55.5,65.5 C55.5,66.6045695 56.4019504,67.5 57.5085302,67.5 L65.4914698,67.5 C66.6007504,67.5 67.5,66.5980496 67.5,65.4914698 L67.5,57.5085302 C67.5,56.3992496 66.6122704,55.5 65.5,55.5 L65.5,55.5 C64.3954305,55.5 63.5,56.4008192 63.5,57.4994651 L63.5,59.6744416 C63.5,60.225142 63.180621,60.3521939 62.7998083,59.9713812 L53.5286188,50.7001917 Z"></path>
                  </g>
                </g>
              </svg>
            </div>
            <input v-if="right" id="size_range" type="range" min="-100" max="100" step="1" v-model="rangeSizeRight" @input="changeSizeRight">
            <input v-else id="size_range" type="range" min="-100" max="100" step="1" v-model="rangeSizeLeft" @input="changeSizeLeft">
          </div>
          <div class="control x">
            <div class="icon x">
              <svg fill="#000000" viewBox="0 0 100 100" x="0px" y="0px">
                <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                  <g fill="#000000">
                    <path d="M56.0023735,47.9543127 L63.6537465,47.9543127 C64.476646,47.9543127 64.6814874,47.4798107 64.0971475,46.8944828 L60.593361,43.3847724 C58.7177994,41.5060397 61.5313905,38.6876915 63.4069522,40.5664242 L71.4378784,48.6701074 C72.1160602,49.3544332 72.1170483,50.4708258 71.4378784,51.161413 L63.4069522,59.3273465 C61.5313905,61.2060792 58.7177994,58.387731 60.593361,56.5089983 L64.0971475,52.9996706 C64.6841748,52.4117148 64.48297,51.9399562 63.6537465,51.9399562 L44.0425728,51.9399562 C44.0275511,51.9399562 44.0125684,51.9397896 43.9976265,51.939458 L36.3462535,51.939458 C35.523354,51.939458 35.3185126,52.41396 35.9028525,52.9992879 L39.406639,56.5089983 C41.2822006,58.387731 38.4686095,61.2060792 36.5930478,59.3273465 L28.5621216,51.2236633 C27.8839398,50.5393375 27.8829517,49.422945 28.5621216,48.7323577 L36.5930478,40.5664242 C38.4686095,38.6876915 41.2822006,41.5060397 39.406639,43.3847724 L35.9028525,46.8941001 C35.3158252,47.4820559 35.51703,47.9538145 36.3462535,47.9538145 L55.9574272,47.9538145 C55.9724489,47.9538145 55.9874316,47.9539812 56.0023735,47.9543127 L56.0023735,47.9543127 Z"></path>
                  </g>
                </g>
              </svg>
            </div>
            <input v-if="right" id="x_range" type="range" min="-100" max="100" step="1" v-model="rangeXRight" @input="changeXRight">
            <input v-else id="x_range" type="range" min="-100" max="100" step="1" v-model="rangeXLeft" @input="changeXLeft">
          </div>
          <div class="control y">
            <div class="icon y">
              <svg fill="#000000" viewBox="0 0 100 100" x="0px" y="0px">
                <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                  <g fill="#000000">
                    <path d="M48.0074273,43.9445119 L48.0074273,36.2931388 C48.0074273,35.4702393 47.5329253,35.2653979 46.9475974,35.8497379 L43.4378871,39.3535243 C41.5591543,41.229086 38.7408062,38.4154948 40.6195389,36.5399332 L48.7232221,28.5090069 C49.4075479,27.8308251 50.5239404,27.8298371 51.2145277,28.5090069 L59.3804611,36.5399332 C61.2591938,38.4154948 58.4408457,41.229086 56.5621129,39.3535243 L53.0527852,35.8497379 C52.4648295,35.2627105 51.9930709,35.4639153 51.9930709,36.2931388 L51.9930709,55.9043126 C51.9930709,55.9193343 51.9929042,55.9343169 51.9925727,55.9492588 L51.9925727,63.6006319 C51.9925727,64.4235314 52.4670747,64.6283728 53.0524026,64.0440328 L56.5621129,60.5402464 C58.4408457,58.6646847 61.2591938,61.4782759 59.3804611,63.3538376 L51.2767779,71.3847638 C50.5924521,72.0629456 49.4760596,72.0639336 48.7854723,71.3847638 L40.6195389,63.3538376 C38.7408062,61.4782759 41.5591543,58.6646847 43.4378871,60.5402464 L46.9472148,64.0440328 C47.5351705,64.6310602 48.0069291,64.4298554 48.0069291,63.6006319 L48.0069291,43.9894581 C48.0069291,43.9744365 48.0070958,43.9594538 48.0074273,43.9445119 L48.0074273,43.9445119 Z"></path>
                  </g>
                </g>
              </svg>
            </div>
            <input v-if="right" id="y_range" type="range" min="-100" max="100" step="1" v-model="rangeYRight" @input="changeYRight">
            <input v-else id="y_range" type="range" min="-100" max="100" step="1" v-model="rangeYLeft" @input="changeYLeft">
          </div>
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
      ],
      rangeSizeLeft: '',
      rangeSizeRight: '',
      rangeXLeft: '',
      rangeXRight: '',
      rangeYLeft: '',
      rangeYRight: '',
      toggleHand: false,
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
    changeSizeLeft: function() {
      const handEl = document.getElementsByClassName('hand-left')[0];
      const handDim = 24;
      const handMod = this.rangeSizeLeft * .1;
      const handNewDim = handDim + handMod + 'rem';

      handEl.style.width = handNewDim;
      handEl.style.height = handNewDim;
    },
    changeSizeRight: function() {
      const handEl = document.getElementsByClassName('hand-right')[0];
      const handDim = 24;
      const handMod = this.rangeSizeRight * .1;
      const handNewDim = handDim + handMod + 'rem';

      handEl.style.width = handNewDim;
      handEl.style.height = handNewDim;
    },
    changeXLeft: function() {
      const handEl = document.getElementsByClassName('hand-left')[0];
      const handDim = -10;
      const handMod = this.rangeXLeft * .1;
      const handNewDim = handDim + handMod + 'vw';

      handEl.style.marginLeft = handNewDim;
    },
    changeXRight: function() {
      const handEl = document.getElementsByClassName('hand-right')[0];
      const handDim = 14;
      const handMod = this.rangeXRight * .1;
      const handNewDim = handDim + handMod + 'vw';

      handEl.style.marginLeft = handNewDim;
    },
    changeYLeft: function() {
      const handEl = document.getElementsByClassName('hand-left')[0];
      const handDim = 0;
      const handMod = this.rangeYLeft * .1;
      const handNewDim = handDim + handMod + 'rem';

      handEl.style.bottom = handNewDim;
    },
    changeYRight: function() {
      const handEl = document.getElementsByClassName('hand-right')[0];
      const handDim = 0;
      const handMod = this.rangeYRight * .1;
      const handNewDim = handDim + handMod + 'rem';

      handEl.style.bottom = handNewDim;
    },
    triggerControls: function() {
      this.toggleHand = !this.toggleHand;
    }
  }
}
</script>


<style lang="scss">

  .hand-unit {

    &.left {

      .hand-tools {
        top: calc(50vh + 3rem);
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
