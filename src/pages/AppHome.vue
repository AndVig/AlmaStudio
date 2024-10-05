<script>
import AppCarouselAuto from '../components/AppCarouselAuto.vue';

export default {
  name: "AppHome",
  components: {
    AppCarouselAuto
  }
};


</script>

<template>
  <div class="container-fluid" >
    <div style="margin-bottom: 5rem;">
      <AppCarouselAuto />
    </div>
    <div class="col-6" >
      <h2 class="text-presentation my-5">  
        Marianna Zupi – Destination Wedding Photographer in italy
      </h2>
      <h3 class="text-desc">
        The job of a wedding photographer is a very strenuous one, the general population can not imagine how much study and sacrifice goes into every shot, a job that is chosen from passion only.
      </h3>
    </div>
  </div>
</template>

<style   scoped>
@import url('https://fonts.googleapis.com/css2?family=Grandiflora+One&display=swap');


.text-presentation{
  font-family: "Grandiflora One";
  font-size: 0.8vw;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 4px;
}
.text-desc{
  font-family: "Grandiflora One";
  font-size: 2vw;
  text-align: center;
  font-weight: 900;
}
</style>
