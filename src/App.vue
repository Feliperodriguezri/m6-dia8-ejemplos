<template>
  <div id="app">
    <h1 :style="{ color: principal }">Titulo principal</h1>

    <div>
      <!-- cambio de Rango de tamaño imagen mendiante %  -->
      <label for="rangeImg">Ancho Imagen</label>
      <input type="range" id="rangeimg" name="vol" value="100" min="20" max="100" step="1" v-model="anchoImagen">
      <span>{{ anchoImagen + '%' }}</span>

      <!-- cambio de Rango de sombra mendiante %  -->
      <label for="sombraImg">sombra imagen</label>
      <input type="range" id="sombraimg" name="vol" value="100" min="20" max="100" step="1" v-model="sombra">

      <!-- cambio de Rango de radius mendiante %  -->
      <label for="radiusImg">border radius imagen</label>
      <input type="range" id="radiusimg" name="vol" value="100" min="20" max="100" step="1" v-model="bordeRedondo">
      <span>{{ anchoImagen + '%' }}</span>
      <figure>
        <img :width="anchoImagen + '%'" src="https://picsum.photos/id/1025/1200/800" alt="" :style="{
          boxShadow: sombraImagen,
          borderRadius: bordeRedondo + '%',
        }" />
      </figure>
    </div>

    <div style="padding: 25px 25px;">
      <p :class="{ realizado: p1 }">Texto de ejemplo1 <input type="checkbox" name="" id="" v-model="p1"> </p>
      <p :class="{ realizado: p2 }">Texto de ejemplo2 <input type="checkbox" name="" id="" v-model="p2"></p>
      <p :class="{ realizado: p3 }">Texto de ejemplo3 <input type="checkbox" name="" id="" v-model="p3"></p>
      <p :class="{ realizado: p4 }">Texto de ejemplo4 <input type="checkbox" name="" id="" v-model="p4"></p>
    </div>

  </div>

</template>

<script>


export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      principal: "blue",
      anchoImagen: 100,
      bordeRedondo: 0,
      sombra: "50px 50px 50px 50px rgba(0, 0, 0, 0.75)",
      p1: false,
      p2: false,
      p3: false,
      p4: false,
    }
  },
  computed: {
    sombraImagen: function () {
      let { sHorizontal, sVertical, sBlurRadius, sSpreadRadius, sColor } = this;
      let boxShadow = `${sHorizontal}px ${sVertical}px ${sBlurRadius}px ${sSpreadRadius}px ${sColor}`;
      return boxShadow;
    }
  }
}
</script>

<style>
.realizado {
  color: red;
  font-weight: 800;
  font-size: 24px;
}
</style>
