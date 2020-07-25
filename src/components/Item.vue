<template>
  <div class='item-unit'>
    <nav class='item-tools'>
      <h1 class='item-title'>Item</h1>
      <div @click="changeItem($event)" class='item-list'>
        <div v-for='item in itemArray' :key='item' class='item-thumb'>
          <img :data-item="`${item}`" class="item-thumb-img" :src="`/assets/accessories/${item}.svg`">
        </div>
      </div>
      <!-- <button @click='randomItem()' class='item-random'>Random item</button> -->
    </nav>
    <div class='item'>
    </div>
  </div>
</template>

<script>

// const itemArray = [
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
  name: 'item',
  data () {
    return {
      randomItem: 'doughnut',
      itemArray: [
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
    // randomItem: function () {
    //   const randomItem = itemArray[Math.floor(Math.random()*itemArray.length)];
    //   const itemEl = document.getElementsByClassName('item')[0];

    //   itemEl.style.backgroundImage = `url('/assets/accessories/${randomItem}.svg')`;
    //   itemEl.className = `item ${randomItem}`;

    //   console.log('item array', itemArray);
    // },
    changeItem: function(event) {
      const accEl = event.target.dataset.item;
      const itemEl = document.getElementsByClassName('item')[0];
      console.log(event.target, accEl);
      console.log(itemEl);
      itemEl.style.backgroundImage = `url('/assets/accessories/${accEl}.svg')`;
    }
  },
  mounted () {

  }
}
</script>


<style lang='scss'>
  .item-tools {
    top: calc(25vh + 1rem);
  }

  .item {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    background: center center no-repeat;
    background-size: contain;
    //
    background-image: url('../assets/accessories/doughnut.svg');
    width: 25rem;
    height: 25rem;
    //
    top: 30rem;
    margin-left: 5vw;
  }

  // button {
  //   background: none;
  //   border: 2px solid black;
  //   padding: 1rem;
  //   font-size: 2rem;
  //   margin-top: 5rem;

  //   &:hover {
  //     cursor: pointer;
  //   }

  //   &:focus {
  //     outline: 1px dashed black;
  //     outline-offset: 2px;
  //   }
  // }
</style>
