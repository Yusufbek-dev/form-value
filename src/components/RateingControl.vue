<template>
  <div>
    <ul>
      <li :class="{ active: modelValue === 'poor' }">
        <button type="button" @click="activate('poor')">Poor</button>
      </li>
      <li :class="{ active: modelValue === 'average' }">
        <button type="button" @click="activate('average')">Average</button>
      </li>
      <li :class="{ active: modelValue === 'great' }">
        <button type="button" @click="activate('great')">Great</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['modelValue'],
  emits:['update:modelValue'],
  // data() {
  //   return {
  //     activeOption: this.modelValue,
  //   };
  // },
  // computed: {
  //   activeOption(){
  //     return this.modelValue
  //   }
  // },
  methods: {
    activate(option) {
      this.$emit('update:modelValue', option)
    },
  },
};
</script>

<style scoped>
.active {
  border-color: red;
}
.active button {
  color: rgba(13, 13, 157, 0.599);
}

ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}
button {
  font: inherit;
  border: none;
  border-color: transparent;
  cursor: pointer;
}
</style>
