<template>
  <p>{{ name }}</p>
  <h1>{{ test }}</h1>
  <p>{{ sampleArray }}</p>
  <li v-for:="array in filterArray" @click="showMyValue(array)">
    {{ array }}
  </li>
  <button @click="emitInput">Emit me for input focus</button>
  <slot></slot>
  <div  class="action">
    <slot name="link"></slot>
  </div>
</template>

<script>
export default {
  props: ["name", "test", "sampleArray"],
  methods: {
    emitInput() {
      this.$emit("inputFocus");
    },
    showMyValue(array) {
      console.log(array);
    },
    filterArray() {
      return this.sampleArray.filter((elem) => {
        return elem > 2;
      });
    },
  },
};
</script>

