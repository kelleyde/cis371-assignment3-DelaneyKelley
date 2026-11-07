  <template>
    <div class="baseBeverage">
    </div>
  </template>

<script setup lang="ts">
// import { ref } from "vue";
// import { computed } from "vue";

//const test_color = "#6B4423";

// // source: https://medium.com/@alemrandev/how-to-use-multiple-v-model-in-a-component-vue-3-75c8c08afed8
// const props = defineProps(['modelValue']);
// const emit = defineEmits(['update:modelValue'])
// console.log("props " + props.modelValue);

// const value = computed({
//   get() {
//     return props.modelValue
//   },
//   set(value: string) {
//     emit("update:modelValue", value)
//   }
// });
// console.log("get value" + value.value);


// source: https://www.youtube.com/watch?v=PTJC46NVHS0&t=40s
// let base_color: string = "#361713";
// const changeColor = (newcolor: string) => {
//   console.log("new color:" + newcolor);
//   base_color = newcolor;
//   console.log("base color:" + base_color);
// }

// const return_base = () => {
//   console.log("return base: " + base_color);
// }

// const colorChange = computed(() => {
//   base_color = props.modelValue;
//   console.log("base color:" + base_color);
//   return base_color;
// })


// emit('update:modelValue', changeColor);

</script>


<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* background-color: v-bind("base_color"); */
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
