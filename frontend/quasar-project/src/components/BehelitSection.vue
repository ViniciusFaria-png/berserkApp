<template>
  <div class="image-container">
    <img
      :src="imageSrc"
      alt="Imagem"
      @mouseenter="hoverIn"
      @mouseleave="hoverOut"
      :style="imageStyle"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageSrc: 'src/assets/Behelito.png',
      imageStyle: {
        transform: 'scale(1)',
        filter: 'brightness(1)',
        transition: 'transform 0.3s, filter 0.3s',
      },
    };
  },
  methods: {
    hoverIn() {
      this.imageStyle.transform = 'scale(1.1)';
      this.imageStyle.filter = 'brightness(1.2)';
    },
    hoverOut() {
      this.imageStyle.transform = 'scale(1)';
      this.imageStyle.filter = 'brightness(1)';
    },
  },
};
</script>

<style scoped>
.image-container {
  display: inline-block;
  position: relative;
}

.image-container img {
  width: 100%;
}
</style>
