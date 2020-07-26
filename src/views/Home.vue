<template>
  <div class="home">
    <div class="monstur-unit">
      <div class="monstur">
        <Head />
        <Face />
        <Item />
        <Hand left />
        <Hand right />
      </div>
      <Name name="Nico"/>
    </div>
    <div class="control-panel">
      <Head />
      <Face />
      <Item />
      <Hand left />
      <Hand right />
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
  },
  mounted () {
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
    transition: background-color 0.1s;
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