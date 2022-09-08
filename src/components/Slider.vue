<template>
  <div class="slider">
    SLIDER
  </div>
</template>

<script>
export default {
  name: 'slider',
  data() {
    return {
      slider: [
        {
          id: 1,
          title: 'Pearls Spring Collection',
          imgLink: 'https://htmldemo.net/corano/corano/assets/img/slider/home3-slide1.jpg',
          infoText: 'New pearl earrings and more from $99',
          animationName: ''
        },
        {
          id: 2,
          title: 'Pearls Spring Collection',
          imgLink: 'https://htmldemo.net/corano/corano/assets/img/slider/home3-slide2.jpg',
          infoText: 'New pearl earrings and more from $99',
          animationName: ''
        },
        {
          id: 3,
          title: 'Pearls Spring Collection',
          imgLink: 'https://htmldemo.net/corano/corano/assets/img/slider/home3-slide3.jpg',
          infoText: 'New pearl earrings and more from $99',
          animationName: ''
        },
      ]
    };
  },
}
</script>
