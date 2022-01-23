<template>
  <div class="w-full mb-6">
    <h4 class="mb-4 font-semibold">Select a color:</h4>
    <div class="flex">
      <button
        v-for="(color, i) in availableColors"
        class="w-8 h-8 mr-2 block"
        :class="[
          i === 0 ? 'border' : '',
          selectedColor === color ? 'border-4 border-red-400' : '',
        ]"
        :key="i"
        :style="{ background: `#${color}` }"
        @click="setActiveColor(color)"
      ></button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    availableColors: { type: Array, required: true },
    setActiveColor: { type: Function, required: true },
    selectedColor: { type: String, required: true },
  },
}
</script>
