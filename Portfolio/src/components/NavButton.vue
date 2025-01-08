<script>
export default {
  props: {
    titlePage: String,
    page: String,
  },
  computed: {
    isActive() {
      return `/${this.page}` === this.$route.path;
    },
  },
  methods: {
    navigate() {
      this.$router.push({ path: `/${this.page}` });
    },
  },
};
</script>

<template>
  <div 
    class="parallelogram" 
    :class="{ active: isActive }" 
    @click="navigate"
  >
    <p class="textBar" :class="{ active: isActive }">
      {{ titlePage }}
    </p>
  </div>
</template>

<style>
.parallelogram {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 225px;
  height: 100%;
  transform: skew(20deg);
  background: #FFF;
  cursor: pointer;
  border-left: 1px solid #000;
  border-right: 1px solid #000;
  transition: background 0.3s ease;
}

.parallelogram:hover {
  background: #8fa6bc;
}

.parallelogram.active {
  background: #4a90e2; 
}

.textBar {
  transform: skew(340deg);
  font-size: 20px;
  opacity: 100%;
}

.textBar.active {
  color: #FFF;
}
</style>
