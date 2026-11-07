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

  <Base v-model = "currentBase.color"></Base>
</template>

<script setup lang="ts">
//import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp, bases, creamers, syrups, currentBase, currentCreamer, currentSyrup } from "./stores/beverage";
import Base from "./components/Base.vue";



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

</style>
