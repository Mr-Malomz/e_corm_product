<template>
  <div class="w-full mb-6">
    <h4 class="mb-4 font-semibold">Add an image:</h4>
    <div class="flex">
      <div
        v-for="image in imageList"
        :key="image.id"
        class="border-2 cursor-pointer mr-2"
        :class="[
          image.publicId === selectedImage ? 'border-red-400 border-4' : '',
        ]"
        @click="setActiveImage(image.publicId)"
      >
        <div v-if="image.id === 1" class="w-11 h-11 bg-white"></div>
        <cld-image v-else :public-id="image.publicId">
          <cld-transformation width="45" height="45" crop="thumb" />
        </cld-image>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imageList: { type: Array, required: true },
    setActiveImage: { type: Function, required: true },
    selectedImage: { type: String, required: true },
  },
}
</script>