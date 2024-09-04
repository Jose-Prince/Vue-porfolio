<template>
  <div class="border-animated">
    <div class="border-top"></div>
    <div class="border-right"></div>
    <div class="border-bottom"></div>
    <div class="border-left"></div>
  </div>
</template>

<script>
export default {
  name: 'AnimatedBorderComponent'
};
</script>

<style scoped>
.border-animated {
  width: 200px;
  height: 200px;
  position: relative;
  background-color: lightgray;
}

.border-top,
.border-right,
.border-bottom,
.border-left {
  position: absolute;
  background-color: red;
  box-sizing: border-box;
}

/* Borde superior */
.border-top {
  top: 0;
  left: 0;
  width: 0;
  height: 5px;
  animation: paint-top 1s forwards;
}

/* Borde derecho */
.border-right {
  top: 0;
  right: 0;
  width: 5px;
  height: 0;
  animation: paint-right 1s 1s forwards; /* Retraso de 1s */
}

/* Borde inferior */
.border-bottom {
  bottom: 0;
  right: 0;
  width: 0;
  height: 5px;
  animation: paint-bottom 1s 2s forwards; /* Retraso de 2s */
}

/* Borde izquierdo */
.border-left {
  bottom: 0;
  left: 0;
  width: 5px;
  height: 0;
  animation: paint-left 1s 3s forwards; /* Retraso de 3s */
}

@keyframes paint-top {
  to {
    width: 100%;
  }
}

@keyframes paint-right {
  to {
    height: 100%;
  }
}

@keyframes paint-bottom {
  to {
    width: 100%;
  }
}

@keyframes paint-left {
  to {
    height: 100%;
  }
}
</style>
