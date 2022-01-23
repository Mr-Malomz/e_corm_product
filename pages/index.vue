<template>
  <div class="flex flex-col items-center p-8">
    <h1 class="text-3xl mb-6 text-indigo-600">Cloudinary Product Customization</h1>
    <section class="flex flex-col lg:flex-row justify-center w-full">
      <ProductImage
        :selectedColor="selectedColor"
        :selectedImage="selectedImage"
        :selectedFont="selectedFont"
        :customText="customText"
        :key="key"
      />
      <div class="w-96 border-l px-4">
        <ColorPicker
          :availableColors="availableColors"
          :setActiveColor="setActiveColor"
          :selectedColor="selectedColor"
        />
        <ColorDropPicker :setActiveColor="setActiveColor" />
        <ImagePicker
          :imageList="imageList"
          :setActiveImage="setActiveImage"
          :selectedImage="selectedImage"
        />
        <TextCustomPicker
          :fontList="fontList"
          :setActiveFont="setActiveFont"
          :setText="setText"
          :selectedFont="selectedFont"
        />
      </div>
    </section>
  </div>
</template>

<script>
import availableColors from '@/utils/availableColors.json'
import imageList from '@/utils/imageList.json'
import fontList from '@/utils/fontList.json'

export default {
  data() {
    return {
      availableColors,
      imageList,
      fontList,
      selectedColor: 'FFFFFF',
      selectedImage: '',
      selectedFont: 'Arial',
      customText: 'Hello',
      key: 0,
    }
  },

  methods: {
    setActiveColor(color) {
      this.selectedColor = color
      this.key++
    },

    setActiveImage(image) {
      this.selectedImage = image
      this.key++
    },

    setActiveFont(font) {
      this.selectedFont = font
      this.key++
    },

    setText(text) {
      this.customText = text
      this.key++
    },
  },
}
</script>