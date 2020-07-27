<template>
  <div class="home">
    <div class="monstur-unit">
      <div class="monstur">
        <Head />
        <Face canvas />
        <Item canvas />
        <Hand canvas left />
        <Hand canvas right />
      </div>
      <Name name="Nico"/>
    </div>
    <div class="control-panel">
      <Face panel />
      <Item panel />
      <Hand panel left />
      <Hand panel right />
    </div>
    <Info />
  </div>
</template>

<script>
import Name from '@/components/Name.vue'
import Head from '@/components/Head.vue'
import Face from '@/components/Face.vue'
import Hand from '@/components/Hand.vue'
import Item from '@/components/Item.vue'
import Info from '@/components/Info.vue'

export default {
  name: 'Home',
  components: {
    Name,
    Head,
    Face,
    Hand,
    Item,
    Info
  },
  methods: {
    scrollBgColor: function() {
      const app = document.getElementById('app');
      const home = document.getElementsByClassName('home')[0];

      app.addEventListener('mousedown', event => {
        let x = event.offsetX / 5;
        let y = event.offsetY / 5;
        let z = x - y;
        let r = 127;
        let g = 255;
        let b = 212;

        let newR = r + x;
        let newG = g - y;
        let newB = b + z;


        if (event.shiftKey) {

          if (newR >= 255) {
            let newR = 255;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else if (newR >= 0) {
            let newR = 0;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else {
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          }

          if (newG >= 255) {
            let newG = 255;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else if (newG >= 0) {
            let newG = 0;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else {
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          }

          if (newB >= 255) {
            let newB = 255;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else if (newB >= 0) {
            let newB = 0;
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          } else {
            home.style.backgroundColor = `rgb(${newR}, ${newB}, ${newG})`;
          }

        }
      });
    },
    resetBgColor: function() {
      const home = document.getElementsByClassName('home')[0];
      let r = 127;
      let g = 255;
      let b = 212;

      document.addEventListener('keyup', function (event) {
        if (event.keyCode === 9) {
          home.style.backgroundColor = `rgb(${r}, ${g}, ${b})`;
        }
      }, false);
    }
  },
  mounted () {
    this.scrollBgColor();
    this.resetBgColor();
  }
}
</script>

<style lang="scss">

  .home {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100vh;
    width: 100vw;
    background: aquamarine;
    transition: background-color 0.3s;
  }

  .monstur-unit {
    width: calc(100vw - 25rem);
    height: 100vh;

    .monstur {
      width: 100%;
      position: relative;
      top: 50%;
      transform: translateY(-50%);
      margin: 3rem 0 0 3vw;
    }

    div[class*="-unit"] {

      div[class*="-tools"] {
        display: none;
      }
    }

    div {

      &.face-unit {

        .face-tools {

        }
      }
    }

    div {

      &[class*="-unit"] {

        .face-tools,
        .item-tools,
        .hand-tools {
          display: none;
        }
      }
    }
  }

  .control-panel {

    .head,
    .face,
    .item,
    .hand {
      display: none;
    }
  }

</style>