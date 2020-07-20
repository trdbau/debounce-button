<template>
  <div>
    <button @click.prevent="handleClick">
      <slot />
    </button>
    <div>clicked: {{ counter }}</div>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    timer: {
      type: Number,
      default: 300
    }
  },
  data: () => ({
    timeOut: null,
    counter: 0
  }),
  methods: {
    handleClick() {
      this.counter += 1;
      clearTimeout(this.timeOut);

      this.timeOut = setTimeout(() => {
        this.$emit("click");
      }, this.timer);
    }
  }
};
</script>

<style lang="scss">
button {
  background-color: white;
  border: 1px solid #000;
  cursor: pointer;
  min-width: 180px;
  outline: none;
  padding: 10px 20px;
  transition: 0.3s;

  &:hover {
    color: white;
    background-color: black;
  }
}
</style>
