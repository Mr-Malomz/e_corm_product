<template>
  <div>
    <cld-image public-id="Hanging_T-Shirt_v83je9" width="500">
      <cld-transformation :effect="`replace_color:${selectedColor}`" />
      <cld-transformation :overlay="selectedImage" fetch-format="auto" width="110" />
      <cld-transformation
        :overlay="{
          fontFamily: selectedFont,
          fontSize: 33,
          fontWeight: 'bold',
          text: text,
        }"
        gravity="center"
        y="0.1"
      />
    </cld-image>
    <p>{{ `#${selectedColor}` }}</p>
    <p>{{ selectedImage }}</p>
    <p>{{ selectedFont }}</p>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  props: {
    selectedColor: { type: String, required: true },
    selectedImage: { type: String, required: true },
    selectedFont: { type: String, required: true },
    text: { type: String, required: true },
  },

}
</script>
