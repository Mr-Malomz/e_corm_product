<template>
  <div class="flex flex-col items-center p-8">
    <h1 class="text-3xl mb-6 text-indigo-600">
      Cloudinary Product Customization
    </h1>
    <section class="flex flex-col lg:flex-row justify-center w-full">
      <ProductImage 
        :selectedColor="selectedColor"
        :selectedImage="selectedImage"
        :selectedFont="selectedFont"
        :text="text"
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
      selectedColor: '47E8D2',
      selectedImage: 'cloudinary-logo',
      selectedFont: 'Arial',
      text: ''
    }
  },

  methods: {
    setActiveColor(color) {
      this.selectedColor = color
      console.log(this.selectedColor)
    },

    setActiveImage(image) {
      this.selectedImage = image
      console.log(this.selectedImage)
    },

    setActiveFont(font) {
      this.selectedFont = font;
      console.log(this.selectedFont);
    },

    setText(text) {
      this.text = text
      console.log(text)
    }
  },
}
</script>
