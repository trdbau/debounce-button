<template>
  <div>
    <div class="container">
      <div>
        <Button @click="addDebounceItem">
          Debounce Button
        </Button>
      </div>
      <div class="split" />
      <div>
        <button @click="addNormalItem">
          Normal Button
        </button>
      </div>
    </div>
    <div class="container">
      <div class="text-only">
        <div>DEBOUNCE TEXT</div>
        <div
          v-for="(item, index) in listDebounceText"
          :key="`debounce_${index}`"
        >
          {{ item }}
        </div>
      </div>
      <div class="text-only">
        <div>NORMAL TEXT</div>
        <div v-for="(item, index) in listNormalText" :key="`normal_${index}`">
          {{ item }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button";
export default {
  name: "Home",
  components: {
    Button
  },
  data: () => ({
    listDebounceText: [],
    listNormalText: []
  }),
  methods: {
    addDebounceItem() {
      this.listDebounceText.push("Text");
    },
    addNormalItem() {
      this.listNormalText.push("Text");
    }
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: space-evenly;
  padding: 80px 0;

  .split {
    border-left: 4px solid black;
  }

  .text-only {
    width: 500px;
  }
}
</style>
