<template>
  <div class="container">
    <Carousel></Carousel>
  </div>
</template>

<script>
import Carousel from "./components/Carousel.vue";

export default {
  name: "App",
  components: { Carousel },
};
</script>

<style lang="scss" scoped>

.container {
  margin: 60px 140px 60px 140px;
}
@media (max-width: 1524px) {
  .container {
    margin: 20px;
  }
}
@media (max-width: 836px) {
  .container {
    margin: 0;
  }
}
</style>
