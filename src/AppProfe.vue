<template>
  <div id="app">
    <h1 :style="{ color: principal }">Titulo principal</h1>

    <div>
      <div>
        <label for="rangeWidth">Ancho imagen: </label>
        <input type="range" id="rangeWidth" name="rangeWidth" min="30" max="100" step="1" v-model="anchoImagen">
        <span>{{ anchoImagen + "%" }}</span>
      </div>
      <div>
        <label for="rangeRadius">Border radius: </label>
        <input type="range" id="rangeRadius" name="rangeRadius" min="0" max="50" step="1" v-model="radiusImagen">
        <span>{{ radiusImagen + "%" }}</span>
      </div>
      <div>
        <hr>
        <span>Sombra horizontal: </span> <input type="range" id="rangeSombraHorizontal" name="rangeSombraHorizontal"
          min="-20" max="30" step="1" v-model="sHorizontal"><span>{{ sHorizontal + "%" }} | </span>

        <span>Sombra Vertical: </span> <input type="range" id="rangeSombraVertical" name="rangeSombraVertical" min="-20"
          max="30" step="1" v-model="sVertical"><span>{{ sVertical + "%" }} | </span>

        <span>Color sombra: </span> <input type="color" id="rangeSombraColor" name="rangeSombraColor"
          v-model="sColor"><span> | </span>


      </div>
      <figure>
        <img :width="anchoImagen + '%'" src="https://picsum.photos/id/1025/1200/800" alt="" :style="{
          boxShadow: sombraImagen,
          '-webkit-box-shadow': sombraImagen,
          '-moz-box-shadow': sombraImagen,
          borderRadius: radiusImagen + '%'
        }" />
      </figure>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      principal: "blue",
      anchoImagen: 100,
      radiusImagen: 0,
      sHorizontal: 10,
      sVertical: 10,
      sBlurRadius: 20,
      sSpreadRadius: 20,
      sColor: "rgba(0,0,0,0.75",
    };
  },
  computed: {
    sombraImagen: function () {
      let { sHorizontal, sVertical, sBlurRadius, sSpreadRadius, sColor } = this;
      let boxShadow = `${sHorizontal}px ${sVertical}px ${sBlurRadius}px ${sSpreadRadius}px ${sColor}`;
      return boxShadow;
    }
  }
};
</script>

<style></style>
