<template>
  <cld-image public-id="Hanging_T-Shirt_v83je9" width="500">
    <!-- <cld-transformation
      :overlay="{
        fontFamily: selectedFont,
        fontSize: 33,
        fontWeight: 'bold',
        text: text,
      }"
      gravity="center"
      color="#666"
    /> -->
    <cld-transformation effect="colorize" :color="`#${selectedColor}`"  fetch-format="auto"/>
    <cld-transformation :overlay="selectedImage" width="1.3" height="1.3" gravity="faces" flags="region_relative" crop="crop" fetch-format="auto"/>
  </cld-image>
</template>

<script>
export default {
  props: {
    selectedColor: { type: String, required: true },
    selectedImage: { type: String, required: true },
    selectedFont: { type: String, required: true },
    text: { type: String, required: true },
  },

  watch: {
    selectedColor(oldColor, newColor) {
        console.log(oldColor, newColor)
      if (oldColor !== newColor) {
          this.$forceUpdate()
      }
    },
  },
}
</script>
