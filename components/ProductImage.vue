<template>
  <div class="lg:h-96">
    <cld-image public-id="Hanging_T-Shirt_v83je9" width="500">
      <cld-transformation :effect="`replace_color:${selectedColor}`" />
      <cld-transformation :overlay="selectedImage" fetch-format="auto" width="110" />
      <cld-transformation
        :overlay="{
          fontFamily: selectedFont,
          fontSize: 33,
          fontWeight: 'bold',
          text: customText,
        }"
        gravity="center"
        y="0.1"
      />
    </cld-image>
  </div>
</template>

<script>
export default {
  props: {
    selectedColor: { type: String, required: true },
    selectedImage: { type: String, required: true },
    selectedFont: { type: String, required: true },
    customText: { type: String, required: true },
  },
}
</script>