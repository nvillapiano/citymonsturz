<template>
  <div class="face-unit">
    <nav class="face-tools">
      <h1 class='face-title'>Face</h1>
      <div @click="changeFace($event)" class='face-list'>
        <!-- angry -->
        <div v-for='angry in angryList' :key='angry' class='face-thumb'>
          <img data-cat="angry" :data-face="`${angry}`" class="face-thumb-img" :src="`/assets/faces/angry/type 0${angry}.svg`">
        </div>
        <!-- confused -->
        <div v-for='confused in confusedList' :key='confused' class='face-thumb'>
          <img data-cat="confused" :data-face="`${confused}`" class="face-thumb-img" :src="`/assets/faces/confused/type 0${confused}.svg`">
        </div>
        <!-- dizzy -->
        <div v-for='dizzy in dizzyList' :key='dizzy' class='face-thumb'>
          <img data-cat="dizzy" :data-face="`${dizzy}`" class="face-thumb-img" :src="`/assets/faces/dizzy/type 0${dizzy}.svg`">
        </div>
        <!-- happy -->
        <div v-for='happy in happyList' :key='happy' class='face-thumb'>
          <img data-cat="happy" :data-face="`${happy}`" class="face-thumb-img" :src="`/assets/faces/happy/type 0${happy}.svg`">
        </div>
        <!-- misc -->
        <div v-for='misc in miscList' :key='misc' class='face-thumb'>
          <img data-cat="misc" :data-face="`${misc}`" class="face-thumb-img" :src="`/assets/faces/misc/type 0${misc}.svg`">
        </div>
        <!-- sad -->
        <div v-for='sad in sadList' :key='sad' class='face-thumb'>
          <img data-cat="sad" :data-face="`${sad}`" class="face-thumb-img" :src="`/assets/faces/sad/type 0${sad}.svg`">
        </div>
        <!-- scared -->
        <div v-for='scared in scaredList' :key='scared' class='face-thumb'>
          <img data-cat="scared" :data-face="`${scared}`" class="face-thumb-img" :src="`/assets/faces/scared/type 0${scared}.svg`">
        </div>
        <!-- tired -->
        <div v-for='tired in tiredList' :key='tired' class='face-thumb'>
          <img data-cat="tired" :data-face="`${tired}`" class="face-thumb-img" :src="`/assets/faces/tired/type 0${tired}.svg`">
        </div>
      </div>
    </nav>
    <div class="face"></div>
  </div>
</template>

<script>
export default {
  name: 'Face',
  data () {
    return {
      angryList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      confusedList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      dizzyList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      happyList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      miscList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      sadList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      scaredList: [
        '1',
        '2',
        '3',
        '4',
        '5',
        '6',
      ],
      tiredList: [
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
    // randomAccessory: function () {
    //   const randomItem = accessoryArray[Math.floor(Math.random()*accessoryArray.length)];
    //   const accessoryEl = document.getElementsByClassName('accessory')[0];

    //   accessoryEl.style.backgroundImage = `url('/assets/accessories/${randomItem}.svg')`;
    //   accessoryEl.className = `accessory ${randomItem}`;

    //   console.log('accessory array', accessoryArray);
    // },
    changeFace: function(event) {
      const faceID = event.target.dataset.face;
      const faceCat = event.target.dataset.cat;
      const faceEl = document.getElementsByClassName('face')[0];
      console.log(event.target, faceID);
      console.log('faceEL', faceEl);
      faceEl.style.backgroundImage = `url('/assets/faces/${faceCat}/type 0${faceID}.svg')`;
    }
  },
}
</script>


<style lang="scss">

  .face-tools {
    top: 0;
  }

  .face {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    background: center center no-repeat;
    background-size: contain;
    //
    background-image: url('/assets/faces/happy/type 01.svg');
    width: 36rem;
    height: 36rem;
    //
    top: 10vh;
    margin-left: 2vw;
  }

  .face-list {
    max-height: 16rem;
  }
</style>
