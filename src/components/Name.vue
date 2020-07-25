<template>
  <div class="name">
    <input required type="text" class="name-input" placeholder="Your monstur name">
  </div>
</template>

<script>
export default {
  name: 'name',
  props: {
    name: String
  }
}
</script>


<style lang="scss">

  .name {
    position: fixed;
    bottom: 4.3rem;
    width: calc(100% - 25rem);
    text-align: center;
    margin-left: 3vw;
  }

  .name-input {
    border: none;
    background: none;
    text-align: center;
    font-size: 3.6rem;
    color: black;
    padding: 1rem 1rem 0;

    &:invalid {
      border-bottom: 2px solid black;
    }

    &:valid {
      border-bottom: 2px solid transparent;
    }

    &:focus {
      outline: 1px dashed rgba(black, 0.2);
      outline-offset: 0;
    }

    &::placeholder {
      color: rgba(black, 0.3);
    }
  }
</style>
