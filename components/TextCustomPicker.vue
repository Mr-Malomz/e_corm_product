<template>
  <div class="w-full mb-6">
    <h4 class="mb-4 font-semibold">Add a text:</h4>
    <form @submit.prevent="onSubmit">
      <select
        v-model="activeFont"
        @change="onChange($event)"
        name="font-picker"
        class="h-10 w-32 mb-3 border rounded"
      >
        <option v-for="(font, i) in fontList" :key="i" :value="font.value">
          {{ font.title }}
        </option>
      </select>
      <div class="flex">
        <input
          type="text"
          placeholder="enter text"
          required
          class="h-10 w-60 mr-2 pl-2 border rounded"
          v-model="text"
        />
        <button class="px-4 bg-indigo-600 text-white rounded">Add Text</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    fontList: { type: Array, required: true },
    setActiveFont: { type: Function, required: true },
    setText: { type: Function, required: true },
    selectedFont: { type: String, required: true },
  },

  data() {
    return {
      activeFont: '',
      text: '',
    }
  },

  methods: {
    onChange(event) {
      this.setActiveFont(event.target.value)
    },

    onSubmit() {
      this.setText(this.text)
    },
  },

  mounted() {
    this.activeFont = this.selectedFont
  },
}
</script>