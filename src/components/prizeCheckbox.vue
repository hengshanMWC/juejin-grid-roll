<template>
  <div class="prize-checkbox">
    <label v-for="prize in prizes" :key="prize.id">
      <span>{{ prize.text }}</span>
      <input
        type="checkbox"
        v-model="value"
        :value="prize.id"
        name="prize"
        :disabled="prize.disabled"
      />
    </label>
  </div>
</template>

<script>
export default {
  name: "prizeCheckbox",
  props: {
    prizes: Array,
  },
  data() {
    return {
      value: [1],
    };
  },
};
</script>

<style lang="scss" scoped>
.prize-checkbox {
  display: flex;
  flex-direction: column;
  margin: 20px;
  label {
    &:not(:last-child) {
      margin-bottom: 5px;
    }
  }
}
</style>
