<template>
    <div id="hub" class="hubBg">
        <h1 class="text-center text-white mt-4 mb-3">
            <b>Our hub</b>
        </h1>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <carousel-3d :controls-visible="true" :display="3" :width="900" :height="505">
                        <slide v-for="(v,k) in 8" :key="'hub'+k" :index="k">
                            <img :src="require('~/assets/img/hub'+v+'.jpg')" alt="" height="100%">
                        </slide>
                    </carousel-3d>
                </div>
            </div>

            <h1 class="text-center text-white mt-4 mb-3">
                <b>Floor Plan</b>
            </h1>

            <div class="row">
                <div class="col-12">
                    <carousel-3d :controls-visible="true" :perspective="0" :space="400" :width="1200" :height="674">
                        <slide v-for="(v,k) in 4" :key="'plan'+k" :index="k">
                            <img :src="require('~/assets/img/plan'+v+'.png')" alt="" height="100%">
                        </slide>
                    </carousel-3d>
                    <!-- <div class="planWrapper">
                        <div class="planImg"><img src="~/assets/img/plan1.png" class="cursor-pointer" width="100%" alt=""></div>
                        <div class="planImg"><img src="~/assets/img/plan2.png" class="cursor-pointer" width="100%" alt=""></div>
                        <div class="planImg"><img src="~/assets/img/plan3.png" class="cursor-pointer" width="100%" alt=""></div>
                        <div class="planImg"><img src="~/assets/img/plan4.png" class="cursor-pointer" width="100%" alt=""></div>
                    </div> -->
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
