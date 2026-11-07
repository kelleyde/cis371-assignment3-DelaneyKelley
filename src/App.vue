<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
      </ul>
      <ul>
      <li>
        <template v-for="base in bases" :key="base.id">
          <label>
            <input
              type="radio"
              name="base.name"
              :id="`r${base}`"
              :value="base"
              v-model="currentBase"
              placeholder="#C8E6C9"
            />
            {{ base.name }}
          </label>
        </template>
      </li>
      </ul>
      <ul>
      <li>
        <template v-for="cream in creamers" :key="cream.id">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${cream}`"
              :value="cream"
              v-model="currentCreamer"
            />
            {{ cream.name }}
          </label>
        </template>
      </li>
      </ul>
      <ul>
      <li>
        <template v-for="syrup in syrups" :key="syrup.id">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>

  <template>
    <div class="baseBeverage">
      <template v-show=changeColor(currentBase.color)></template>
    </div>
  </template>

  <template>
  <div class="froth">
    <div v-for=" in 5" class="foam"></div>
  </div>
  </template>

  <template>
  <div class="syrup">
    <template v-show="changeSyrupColor(currentSyrup.color)"></template>
  </div>
  </template>

</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import { temps, currentBase, currentTemp, bases, creamers, syrups, currentCreamer, currentSyrup } from "./stores/beverage";
// import Base from "./components/Base.vue";

// source: https://www.youtube.com/watch?v=PTJC46NVHS0&t=40s
const base_color = ref<string>("#361713");
const changeColor = (newcolor: string) => {
  console.log("new color:" + newcolor);
  base_color.value = newcolor;
  console.log("base color:" + base_color.value);
}

const syrup_color = ref<string>("#c6c6c6");
const changeSyrupColor = (newcolor: string) => {
  console.log("new color:" + newcolor);
  syrup_color.value = newcolor;
  console.log("syrup color:" + syrup_color.value);
}


</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}

.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  background-color: v-bind(base_color);
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}

.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  background: v-bind(syrup_color);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}

</style>
