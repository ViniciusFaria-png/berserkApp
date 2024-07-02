<template>
  <div class="image-container">
    <div class ="content__above">
      <p class="eclipse__name"> Eclipse de <span class="eclipse__kingName">Guts</span></p>
      <div class="sacrifice__countX">
        <h3 class="sacrifice__text"><span class="sacrifice__count">{{ sacrificeCount }}</span> sacrifícios</h3>
        <p class="sacrifice__sec">
          por segundo:
          <span class="sacrifice__secText">{{ sacrificePerSecond }}</span>
        </p>
      </div>
    </div>

    <img
      :src="imageSrc"
      alt="Imagem"
      @mouseenter="hoverIn"
      @mouseleave="hoverOut"
      @mousedown="mousedownEffect"
      @mouseup="mouseupEffect"
      @click="incrementSacrificeCount"
      :style="imageStyle"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageSrc: 'src/assets/Behelito.png',
      backgroundSrc: 'src/assets/bg2.png',
      imageStyle: {
        transform: 'scale(1)',
        filter: 'brightness(1)',
        transition: 'transform 0.3s, filter 0.3s',
      },

      sacrificeCount: 0,
      sacrificePerSecond: 0,
    };
  },
  methods: {
    // clickBehelit(){
    //   this.imageStyle.transition ='transform 0.3s, filter 0.3s';
    //   this.imageStyle.transform = 'scale(0.9)';

    //   setTimeout(() => {
    //     this.imageStyle.transition ='transform 0.3s, filter 0.3s';
    //     this.imageStyle.transform = 'scale(1.1)';
    //   }, 100);
    // },

    mousedownEffect(){
      this.imageStyle.transform = 'transform 0.3s';
      this.imageStyle.transform = 'scale(0.9)';
    },
    mouseupEffect(){
      this.imageStyle.transition = 'transform 0.3s'; // Transição rápida de volta
      this.imageStyle.transform = 'scale(1.1)'; // Retorna ao tamanho original
      setTimeout(() => {
        this.imageStyle.transition = 'transform 0.3s, filter 0.3s'; // Restabelece a transição original
      }, 100);
    },
    hoverIn() {
      this.imageStyle.transform = 'scale(1.1)';
      this.imageStyle.filter = 'brightness(1.2)';
    },
    hoverOut() {
      this.imageStyle.transform = 'scale(1)';
      this.imageStyle.filter = 'brightness(1)';
    },
    incrementSacrificeCount(){
      this.sacrificeCount++;
    }
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Palanquin+Dark:wght@400;500;600;700&display=swap');

html, body{
  margin: 0;
  height: 100%;
}
h1,h2,h3,h4,h5,h6,p{
  margin: 0;
  color: rgb(255, 255, 255);
}

.image-container img {
  max-width: 100%;
  max-height: 100%;
  position: relative;
  object-fit: contain;
}


.image-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 32%;
  height: 100vh;
  border-right: 16px solid transparent;
  border-image: url("../assets/Y_line.png") 1% 100% repeat;
  background-image: url('src/assets/bg2.png');
  background-size: auto;
  background-repeat: repeat;
  background-position: center;
  overflow: hidden;
}

.content__above{
  position: absolute;
  top: 10%;
  width: 100%;
  text-align: center;
  z-index: 2;
}

.eclipse__name{
  width: 75%;
  margin: 0 auto 10px auto;
  padding: 1px 6px;
  font-size: 20px;
  text-align: center;
  border-radius: 10px;
  background-color: rgba(0,0,0,0.4);
  z-index: 3;
  cursor: pointer;
}

.eclipse__name:hover{
    color: white;
    text-shadow: 1px 1px 9px white;
}

.sacrifice__countX{
    text-align: center;
    position: relative;
    z-index: 3;
    background-color: rgba(0,0,0,0.4);
}

.sacrifice__text{
    font-size: 28px;
    line-height: 1;
}
.sacrifice__sec{
    font-size: 14px;
    font-weight: 700;
}

</style>
