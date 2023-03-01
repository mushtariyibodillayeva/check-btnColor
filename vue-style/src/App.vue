<template>
  <div class="card container">
    <img
      :src="imageUrl"
      :style="{
        filter: `hue-rotate(${hueRotate}deg)`,
        backgroundColor: selectedColor,
      }"
    />
    <div class="color-picker">
      <!-- label1 -->
      <label for="color1">
        <input
          type="radio"
          name="color"
          id="color1"
          value="#ff0000"
          @change="selectColor"
        />
        <span class="color-swatch" style="background-color: #ff0000"></span>
      </label>

      <label for="color2">
        <input
          type="radio"
          name="color"
          id="color2"
          value="green"
          @change="selectColor"
        />
        <span class="color-swatch" style="background-color: green"></span>
      </label>
      <label for="color3">
        <input
          type="radio"
          name="color"
          id="color3"
          value="#0000ff"
          @change="selectColor"
        />
        <span class="color-swatch" style="background-color: #0000ff"></span>
      </label>
    </div>
    <div class="counter">
      <button @click="decrement">-</button>
      <span class="number1">{{ count }}</span>
      <button @click="increment">+</button>
    </div>
    <button type="submit" class="btn">Submit</button>
  </div>
</template>

<script>
export default {
  name: "Card",
  data() {
    return {
      count: 0,
      selectedColor: "#fff",
      imageUrl: "",
      hueRotate: 0,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      if (this.count > 0) {
        this.count--;
      }
    },
    selectColor(event) {
      this.selectedColor = event.target.value;
      this.hueRotate = Math.floor(Math.random() * 360);
    },
  },
};
</script>

<style scoped></style>
