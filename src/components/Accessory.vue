<template>
  <div class='accessory-unit'>
    <nav class='accessory-tools'>
      <h1 class='accessory-title'>Choose Accessory</h1>
      <div @click="changeAccessory($event)" class='accessory-list'>
        <div v-for='item in accessoryArray' :key='item' class='accessory-thumb'>
          <img :data-accessory="`${item}`" class="accessory-thumb-img" :src="`/assets/accessories/${item}.svg`">
        </div>
      </div>
      <button @click='randomAccessory()' class='accessory-random'>Random Accessory</button>
    </nav>
    <div class='accessory'>
    </div>
  </div>
</template>

<script>

// const accessoryArray = [
//   'doughnut',
//   'coffee',
//   'ice cream',
//   'candy',
//   'fruit',
//   'bowl',
//   'bread',
//   'book',
//   'ball',
// ];

export default {
  name: 'Accessory',
  data () {
    return {
      randomItem: 'doughnut',
      accessoryArray: [
        'doughnut',
        'coffee',
        'ice cream',
        'candy',
        'fruit',
        'bowl',
        'bread',
        'book',
        'ball',
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
    changeAccessory: function(event) {
      const accEl = event.target.dataset.accessory;
      const accessoryEl = document.getElementsByClassName('accessory')[0];
      accessoryEl.style.backgroundImage = `url('/assets/accessories/${accEl}.svg')`;
    }
  },
  mounted () {

  }
}
</script>


<style lang='scss'>
  .accessory-tools {
    top: 1 * 25vh;

    .accessory-title {
      font-size: 2.4rem;
    }

    .accessory-list {
      display: flex;
      flex-wrap: wrap;
      width: 16rem;

      .accessory-thumb {
        width: 4rem;
        display: flex;
        align-items: center;
        justify-content: center;

        img {

        }
      }
    }

    &:hover {
      cursor: pointer;
    }
  }

  .accessory {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
    margin-top: 15%;
    width: 120px;
    height: 120px;
    background: center center no-repeat;
    background-image: url('../assets/accessories/book.svg');
    background-size: contain;
  }

  button {
    background: none;
    border: 2px solid black;
    padding: 1rem;
    font-size: 2rem;
    margin-top: 5rem;

    &:hover {
      cursor: pointer;
    }

    &:focus {
      outline: 1px dashed black;
      outline-offset: 2px;
    }
  }
</style>
