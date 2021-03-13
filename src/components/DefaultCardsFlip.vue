<template>
  <div id="flipperContainer">
    <div class="flipperCard">
      <div class="front">
      </div>
      <div class="back">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardFlip",
}
</script>

<style lang="css" scoped>

/* entire container, keeps perspective */

#flipperContainer, .front, .back {
  width: 80px;
  height: 100px;
}

/* flip speed goes here */
.flipperCard {
  transition: 0.6s;
  transform-style: preserve-3d;
  position: relative;
  -webkit-animation-name: flip;
  animation-name: flip;
  -webkit-animation-duration: 0.6s;
  animation-duration: 0.6s;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-delay: 3s;
  animation-delay: 2s;
}

/* hide back of pane during swap */
.front, .back {
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
}

/* front pane, placed above back */
.front {
  background: url("../assets/back.png") no-repeat;
  /* for firefox 31 */
  transform: rotateY(0deg);
}

/* back, initially hidden pane */
.back {
  transform: rotateY(180deg);
  background: url("../assets/front.png") no-repeat;
}

@keyframes flip {
  from { -webkit-transform: rotateY(0deg); transform: rotateY(0deg); }
  to { -webkit-transform: rotateY(180deg); transform: rotateY(180deg); }
}


</style>
