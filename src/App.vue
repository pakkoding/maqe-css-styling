<template>
  <div id="container">
    <div id="main-square">
      <div id="windows-frame">
        <div id="sub-square-top-left">
          <div class="sub-square-text">M</div>
        </div>
        <div id="sub-square-top-right">
          <div class="sub-square-text">A</div>
        </div>
        <div id="sub-square-bottom-left">
          <div class="sub-square-text">Q</div>
        </div>
        <div id="sub-square-bottom-right">
          <div class="sub-square-text">E</div>
        </div>
        <div id="square-shadow"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CSS-Styling",
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@500&display=swap");
$main-square-background-color: linear-gradient(
        180deg,
        rgba(106, 196, 232, 1) 0%,
        rgba(156, 212, 209, 1) 100%
);
$sub-square-background-color: #ffffff;
$sub-square-box-shadow-color: #686767;
$sub-square-text-color: #67C3E9;

#container {
  font-family: "Roboto", sans-serif;
  display: grid;
  justify-content: center;
  align-content: center;
  height: 100vh;
  background: #F7F7F7;
}
#main-square {
  width: 500px;
  height: 500px;
  background: $main-square-background-color;
  position: relative;
  display: grid;
  align-content: center;
  justify-content: center;
  border-radius: 10px;
  box-shadow: 0 0 0 10px white,
              0 0 0 20px #67C3E9,
              20px 20px 20px 5px #C2C2C2;

  #windows-frame {
    width: 400px;
    height: 400px;
    position: relative;
  }

  #square-shadow {
    z-index: 0;
    width: 280px;
    height: 280px;
    background: #9CD6E4;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  #sub-square-top-left {
    z-index: 1;
    position: absolute;
    top: 0;
    left: 0;
    transform: translate(-4px, -4px);
    background: $sub-square-background-color;
    @extend .sub-square-box-size, .sub-square-shadow;
  }
  #sub-square-top-right {
    z-index: 1;
    position: absolute;
    top: 0;
    right: 0;
    transform: translate(4px, -4px);
    background: $sub-square-background-color;
    @extend .sub-square-box-size, .sub-square-shadow;
  }
  #sub-square-bottom-left {
    z-index: 1;
    position: absolute;
    bottom: 0;
    left: 0;
    transform: translate(-4px, 4px);
    background: $sub-square-background-color;
    @extend .sub-square-box-size, .sub-square-shadow;
  }
  #sub-square-bottom-right {
    z-index: 1;
    position: absolute;
    bottom: 0;
    right: 0;
    transform: translate(4px, 4px);
    background: $sub-square-background-color;
    @extend .sub-square-box-size, .sub-square-shadow;
  }

  .sub-square-shadow {
    box-shadow: inset 2px 2px 12px -1px $sub-square-box-shadow-color;
  }

  .sub-square-box-size {
    width: 180px;
    height: 180px;
    border-radius: 3px;
  }

  .sub-square-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: $sub-square-text-color;
    font-size: 5em;
    text-shadow: 0.2px 0.2px 2px #666666;
  }
}
</style>