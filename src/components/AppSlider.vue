<template>
  <div class="bg-zinc-300 min-h-screen flex flex-col items-center justify-center">
    <h1 class="text-2xl pt-10 mb-6">
      Inline Range Slider
    </h1>
    <div class="container bg-white p-10 rounded-xl shadow-2xl max-w-4xl w-full">
      <div class="flex justify-between items-center mb-10">
        <div class="w-4/10">
          <label for="slider" class="block text-xl mb-4">Test Control</label>
          <input
            id="slider"
            type="range"
            :min="minimumValue"
            :max="maximumValue"
            :step="actualStepValue"
            v-model="currentValue"
            class="w-[300%] h-4 bg-gray-300 rounded-lg overflow-hidden appearance-none"
          />
        </div>
        <div class="text-xl font-bold bg-gray-300 p-5 rounded-lg shadow-xl">
          <span>Current Value: {{ currentValue }}</span>
        </div>
      </div>
  
      <div class="flex justify-between space-x-6">
        <div class="settings w-1/3">
          <label for="stepValue" class="text-xl inline-flex items-center">
            Step Value:
            <InfoIcon class="ml-2"/>
          </label>
          <input type="number" id="stepValue" v-model.number="stepValue" class="mt-2 border p-2 text-lg rounded w-full" />
        </div>
  
        <div class="settings w-1/3">
          <label for="minValue" class="block text-xl">Minimum Value:</label>
          <input type="number" id="minValue" v-model.number="minimumValue" class="mt-2 border p-2 text-lg rounded w-full" />
        </div>
  
        <div class="settings w-1/3">
          <label for="maxValue" class="block text-xl">Maximum Value:</label>
          <input type="number" id="maxValue" v-model.number="maximumValue" class="mt-2 border p-2 text-lg rounded w-full" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import InfoIcon from '../components/icons/InfoIcon.vue';

export default {
  name: "AppSlider",
  components: {
    InfoIcon,
  },
  data() {
    return {
      currentValue: 0,
      stepValue: 0,
      minimumValue: 0,
      maximumValue: 100,
    };
  },
  computed: {
    actualStepValue() {
      return this.stepValue === 0 ? 0.00000000000001 : this.stepValue;
    }
  },
  watch: {
    minimumValue(newVal) {
      if (this.currentValue < newVal) {
        this.currentValue = newVal;
      }
    },
    maximumValue(newVal) {
      if (this.currentValue > newVal) {
        this.currentValue = newVal;
      }
    },
  },
};
</script>

<style scoped>

/* Custom Range Slider */

#slider {
  -webkit-appearance: none;
  appearance: none;
  height: 18px !important;
  width: 300%;
  border-radius: 10em;
  background-color: #cd7228;
  outline: none;
  margin-bottom: 14px;
}

#slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #f4f4f4;
  cursor: pointer;
  border: 3px solid #f4f4f4;
}


#slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background-color: #cd7228;
  cursor: pointer;
  border: 3px solid #f4f4f4;
}

#output {
 color: #cd7228;
 font-family: 'Roboto', sans-serif;
 letter-spacing: 1.5px;
 font-size: 20px;
 margin-left: 5px;
}


</style>
