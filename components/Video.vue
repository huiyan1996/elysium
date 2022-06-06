<template>
  <div class="videoWrapper py-5">
        <div class="text-center px-3 cursor-pointer" @click="videoModal=!videoModal">
            <img src="~/assets/img/playButton.png" class="img-fluid" alt="">
        </div>

        <b-modal 
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
                <source src="~/assets/img/video.mp4" type="video/mp4">
            </video>
        </b-modal>
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
