<template>
  <div class="carousel">
    <transition name="fade" mode="out-in">
      <img :key="currentImage" :src="currentImage" alt="Immagine del carosello" draggable="false" />
    </transition>
  </div>
</template>

<script>
export default {
  name: "AppCarouselAuto",
  data() {
    return {
      images: [
        '/images/1.jpg',
        '/images/2.jpg',
        '/images/3.JPG',
        '/images/4.JPG',
      ],
      currentImage: "",
      currentIndex: 0,
    };
  },
  mounted() {
    this.currentImage = this.images[0];
    this.startCarousel();
  },
  methods: {
    startCarousel() {
      setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
        this.currentImage = this.images[this.currentIndex];
      }, 5000);
    },
  },
};
</script>

<style scoped>
.carousel {
  width: 90%;
  height: 80%;
  overflow: hidden;
  /* box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); */
}

.carousel img {
  width: 100%;
  height:fit-content;
  object-fit:contain;
  transition: opacity 0.7s ease-in-out;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>