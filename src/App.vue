<template>
  <div id="app">
    <div class="np-img-container">
      <img
        v-bind:class="['np-img-image', 'np-img-image-' + selectedFilter]"
        src="https://i.ibb.co/89KVhPQ/girl-filter.jpg"
        alt="np-image-preview"
      />
    </div>
    <div>
      <div class="np-filters-container">
        <div v-for="filter in 12" :key="filter" :class="['np-filter-img']">
          <div @click="applyFilter(filter)">Filter {{ filter }}</div>
        </div>
      </div>
    </div>
    <div class="np-credits">www.nightprogrammer.com</div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      selectedFilter: 1,
    };
  },
  methods: {
    applyFilter(filterIndex) {
      this.selectedFilter = filterIndex;
      console.log(this.selectedFilter);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.np-img-image {
  height: 300px;
  border-radius: 6px;
}
.np-filters-container {
  max-width: 430px;
}
.np-filter-img {
  display: inline-block;
  margin-right: 8px;
  margin-top: 8px;
  height: 20px;
  background: #833bbe;
  border-radius: 6px;
  color: #fff;
  padding: 10px 0px;
  min-width: 80px;
  text-align: center;
  cursor: pointer;
}
.np-filter-img:hover {
  background: #b160f3;
  transition: all 0.3s;
}
.np-filter-img:focus {
  background: #4a1972;
  transition: all 0.3s;
}
.np-img-image-1 {
  filter: unset;
}
.np-img-image-2 {
  filter: brightness(200%);
}
.np-img-image-3 {
  filter: contrast(200%);
}
.np-img-image-4 {
  filter: drop-shadow(8px 8px 10px gray);
}
.np-img-image-5 {
  filter: grayscale(100%);
}
.np-img-image-6 {
  filter: blur(5px);
}
.np-img-image-7 {
  filter: hue-rotate(90deg);
}
.np-img-image-8 {
  filter: invert(100%);
}
.np-img-image-9 {
  filter: opacity(30%);
}
.np-img-image-10 {
  filter: saturate(8);
}
.np-img-image-11 {
  filter: sepia(100%);
}
.np-img-image-12 {
  filter: contrast(200%) brightness(150%);
}
.np-credits {
  font-size: 12px;
  margin-top: 12px;
}
</style>