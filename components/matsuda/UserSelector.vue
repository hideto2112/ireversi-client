<template>
  <div class="users">
    <div
      v-for="n in number"
      :key="n"
      :style="current === n ? 'background: #f77' : ''"
      @click="changeCurrent(n)"
    >{{ n }}</div>
  </div>
</template>

<script>
export default {
  props: ['number', 'current'],
  methods: {
    changeCurrent(n) {
      this.$emit('change', n);
    },
  },
};
</script>

<style scoped>
.users {
  position: fixed;
  bottom: 0;
  left: 0;
  background: #fff;
  width: 100px;
}

.users > div {
  box-sizing: border-box;
  width: 50%;
  height: 50px;
  border-radius: 5px;
  border: 2px solid #555;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  font-size: 150%;
  cursor: pointer;
}

.users > div:hover {
  background: #ccc;
}
</style>
