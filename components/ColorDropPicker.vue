<template>
  <div class="w-full mb-6">
    <h4 class="mb-2 font-semibold">Add a custom color:</h4>
    <input
      type="color"
      name=""
      id=""
      class="h-9 w-20 border-2 cursor-pointer"
      @change="onChange"
    />
  </div>
</template>

<script>
export default {
  props: {
    setActiveColor: { type: Function, required: true },
  },
  methods: {
    onChange(event) {
      this.setActiveColor(event.target.value.slice(1))
    },
  },
}
</script>