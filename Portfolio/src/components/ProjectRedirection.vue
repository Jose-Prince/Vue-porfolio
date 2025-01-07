<script>
export default {
  name: 'AnimatedBorderComponent',
  props: {
    label: String
  }
};
</script>

<template>
  <div class="redirection-style">
    <div class="border-animated">
      {{ label }}
      <div class="box"></div>
    </div>
  </div>
</template>


<style scoped>

.redirection-style {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
}
.border-animated {
  padding: 0px;
  font-size: 2vw;
  height: auto;
  border-bottom: #000;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
}

.border-bottom {
  color: #000;
  margin: 0;
  font-size: 10px;
  background-color: white;
  box-sizing: border-box;
}

/* Borde inferior */
.border-bottom {
  height: auto;
  animation: paint-bottom 1s 2s forwards; /* Retraso de 2s */
}

@keyframes paint-bottom {
  to {
    width: 100%;
  }
}

.box {
  width: 200px;
  height: 10px;
  position: relative;
  background-color: lightgray;
}

.box::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  height: 5px; /* Grosor del borde */
  width: 0; /* Comienza con 0 de ancho */
  background-color: red;
  transition: width 1s ease; /* Duración y tipo de transición */
}

.box:hover::before {
  width: 100%; /* Ancho completo en hover */
}

</style>
