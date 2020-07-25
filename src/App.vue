<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view/>
  </div>
</template>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }

// #nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }

*,
*::before,
*::after {
  box-sizing: border-box;
}

body, html {
  margin: 0;
  padding: 0;
  font-size: 62.5%; // 1rem = 10px
}

h1,
h2,
h3,
h4,
h5,
h6,
input,
a {
  margin: 0;
  font-family: 'Arial Rounded MT Bold', 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

img {
  display: block;
  max-width: 100%;
}

nav {
  position: fixed;
  right: 0;
  // height: 25vh;
  overflow: scroll;
  padding: 2rem 2rem 2rem 0;
  width: 25rem;
  max-width: 33vw;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;

  h1 {
    width: 100%;
  }

  h1[class*="-title"] {
    font-size: 2.4rem;
    text-align: center;
    border-bottom: 2px solid black;
    padding-bottom: 0.4rem;
    margin: 1rem 0;
  }

  div[class*="-list"] {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    flex-wrap: wrap;
    overflow: scroll;
  }

  div[class*="-thumb"] {
    width: 25%;
    max-height: 6rem;
    display: flex;
    align-items: center;
    justify-content: center;

    &:not(.face-thumb) {
      padding: 1rem;
      margin-bottom: -1rem;
    }

    &:hover {
      cursor: pointer;
    }
  }
}


</style>
