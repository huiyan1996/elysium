<template>
  <div class="videoWrapper py-5">

        <div class="d-flex justify-content-center">
            <video width="800px" controls class="img-fluid">
                <source src="https://elui.mlitteam.co/assets/playos.mp4" type="video/mp4">
            </video>
        </div>
        

        <!-- <div class="text-center px-3 cursor-pointer" @click="videoModal=!videoModal">
            <img class="thumbNail img-fluid" src="~/assets/img/passThumb.png" alt="" width="500px">
        </div> -->

        <!-- <b-modal 
            v-model="videoModal" 
            size="xl" 
            hide-footer 
            hide-header
            centered
            body-class="bg-black"
        >
            <div class="text-right mb-3">
                <button class="btn btn-default text-white" @click="videoModal=!videoModal">
                    <b-icon icon="x-lg" />
                </button>
            </div>
            <video width="100%" controls>
                <source src="https://elui.mlitteam.co/assets/playos.mp4" type="video/mp4">
            </video>
        </b-modal> -->
  </div>
</template>

<script>
export default {
  name: 'Banner',
  data() {
      return {
          videoModal: false,
      }
  },
}
</script>