<template>
  <div class="info">
    <header>
      <h1><a href="https://www.instagram.com/citymonsturz/" target="_blank" rel="noopenner">@Citymonsturz</a></h1>
      <h3>

      </h3>
    </header>
    <footer>
      <h3>Illustrations by <a href="https://www.instagram.com/sloetoe/" target="_blank" rel="noopener">@sloetoe</a></h3>
      <h3>Website by <a href="https://www.illapiano.com/" target="_blank" rel="noopener">@illapiano</a></h3>
      <h3>Inspired by Open Peeps <a href="https://www.instagram.com/pablostanley/" target="_blank" rel="noopener">@pablostanley</a></h3>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'info'
}
</script>


<style lang="scss">

  .info {
    position: fixed;
    top: 0;
    left: 2rem;
    text-align: left;

    h1 {
      font-size: 4.8rem;
      margin: 2rem 0 0 0;
    }

    h3 {
      font-size: 2.4rem;
    }

    a {
      display: inline-block;
    }


    h3 {

      a {
        margin: 0.5rem 0 0 0;
      }
    }

    header {

      h3 {
        font-size: 1.8rem;
      }
    }

    footer {
      margin-top: 2rem;

      h3 {
        font-size: 1.4rem;
        height: 2.3rem;
      }
    }
  }

</style>
