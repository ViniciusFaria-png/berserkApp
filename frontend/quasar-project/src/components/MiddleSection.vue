<template>
  <div class="middle-container">
    <div class ="content__above">
      <p class="custom__name"> Custom</p>
    </div>
  </div>
</template>


<style>

.middle-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 33.33%;
  height: 100vh;
  border-right: 16px solid transparent;
  border-image: url("../assets/Y_line.png") 1% 100% repeat;
  background-image: url('src/assets/bg2.png');
  background-size: auto;
  background-repeat: repeat;
  background-position: center;
  overflow: hidden;
}

.custom__name{
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

.custom__name:hover{
    color: white;
    text-shadow: 1px 1px 9px white;
}
</style>
