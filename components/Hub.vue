<template>
    <div id="hub" class="hubBg">
        <h1 class="text-center text-white mt-4 mb-3">
            <b>Our hub</b>
        </h1>
        <div class="container">
            <div class="row">
                <div class="col-md-6 mb-4">
                    <img src="~/assets/img/hub1.png" class="cursor-pointer" width="100%" alt="" @click="(event) => openImg(event)">
                </div>
                <div class="col-md-6 mb-4">
                    <img src="~/assets/img/hub2.png" class="cursor-pointer" width="100%" alt="" @click="(event) => openImg(event)">
                </div>
                <div class="col-md-6 mb-4">
                    <img src="~/assets/img/hub3.png" class="cursor-pointer" width="100%" alt="" @click="(event) => openImg(event)">
                </div>
                <div class="col-md-6 mb-4">
                    <img src="~/assets/img/hub4.png" class="cursor-pointer" width="100%" alt="" @click="(event) => openImg(event)">
                </div>
            </div>
        </div>

        <b-modal 
            v-model="imgModal" 
            size="xl" 
            hide-footer 
            hide-header
            centered
            body-class="bg-black"
        >
            <div class="text-right mb-3">
                <button class="btn btn-default text-white" @click="imgModal=!imgModal">
                    <b-icon icon="x-lg" />
                </button>
            </div>
            <img :src="imgSrc" width="100%" alt="">
        </b-modal>
    </div>
</template>

<script>
export default {
  name: 'RoadMap',
  data() {
      return {
        imgSrc: "",
        imgModal: false,
      }
  },
  methods: {
    openImg(s) {
        this.imgSrc = s.target.src
        this.imgModal = true
    }
  },
}
</script>
