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

::selection {
  color: black;
  background-color: transparent;
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

a {
  color: black;
  text-decoration: none;
  transition: all 0.15s;
  position: relative;

  &::before {
    content: '';
    position: absolute;
    top: 2%;
    left: -4%;
    width: 0;
    height: 108%;
    background: white;
    z-index: -1;
    pointer-events: none;
    transition: all 0.15s;
  }

  &:hover {

    &::before {
      width: 108%;
    }
  }
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
    text-align: left;
    border-bottom: 2px solid black;
    padding-bottom: 0.4rem;
    padding-left: 1rem;
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

input[type=range] {
  -webkit-appearance: none; /* Hides the slider so that custom slider can be made */
  width: 100%; /* Specific width is required for Firefox. */
  background: transparent; /* Otherwise white in Chrome */

  &::-webkit-slider-thumb {
    -webkit-appearance: none;
  }

  &:focus {
    outline: none; /* Removes the blue border. You should probably do some kind of focus styling for accessibility reasons though. */
  }

  &::-ms-track {
    width: 100%;
    cursor: pointer;

    /* Hides the slider so custom styles can be added */
    background: transparent;
    border-color: transparent;
    color: transparent;
  }
}

input[type=range] {
  background: black;
  height: 1rem;
  border-radius: 4px;
  // overflow: hidden;

  &::-webkit-slider-thumb {
    -webkit-appearance: none;
    border: 2px solid black;
    height: 2rem;
    width: 1rem;
    border-radius: 4px;
    background: white;
    cursor: pointer;
    margin: 0; /* You need to specify a margin in Chrome, but in Firefox and IE it is automatic */
  }
  :active {
    cursor: grabbing;
    cursor: -moz-grabbing;
    cursor: -webkit-grabbing;
  }
}

// /* Special styling for WebKit/Blink */
// input[type=range]::-webkit-slider-thumb {
//   -webkit-appearance: none;
//   border: 1px solid #000000;
//   height: 36px;
//   width: 16px;
//   border-radius: 3px;
//   background: #ffffff;
//   cursor: pointer;
//   margin-top: -14px; /* You need to specify a margin in Chrome, but in Firefox and IE it is automatic */
//   box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d; /* Add cool effects to your sliders! */
// }

// /* All the same stuff for Firefox */
// input[type=range]::-moz-range-thumb {
//   box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
//   border: 1px solid #000000;
//   height: 36px;
//   width: 16px;
//   border-radius: 3px;
//   background: #ffffff;
//   cursor: pointer;
// }

// /* All the same stuff for IE */
// input[type=range]::-ms-thumb {
//   box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
//   border: 1px solid #000000;
//   height: 36px;
//   width: 16px;
//   border-radius: 3px;
//   background: #ffffff;
//   cursor: pointer;
// }

  div[class*="-trigger"] {
    position: absolute;
    top: 3.3rem;
    right: 3rem;
    width: 2rem;
    transition: all 0.3s;

    &:hover {
      cursor: pointer;
      transform: rotate(45deg);
    }

    &.primary {
      width: 3.3rem;
      top: 2.6rem;

      &:hover {
        transform: scale(1.1);
      }
    }
  }

  div[class*="-panel"] {
    position: relative
  }

  div[class*="-controls"] {
    position: absolute;
    top: 0;
    background: aquamarine;
    height: 100%;
    width: 100%;
    opacity: 0;
    pointer-events: none;

    .control {
      display: flex;
      align-items: center;
      justify-content: space-between;

      .icon {
        width: 4rem;
        height: 4rem;
      }

      input {
        width: 100%;
        margin-top: -0.6rem;
      }
    }

    &.show {
      opacity: 1;
      pointer-events: all;
    }
  }

</style>
