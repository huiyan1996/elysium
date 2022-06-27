<template>
  <div class="passWrapper">
    <div class="container">
        <div class="row">
            <div class="col-md-6 py-md-5 py-2">
                <img src="~/assets/img/passDesign.png" class="img-fluid" alt="">
            </div>
            <div class="col-md-6 py-md-5 py-2" id="pass">
                <h2 class="font2"><span class="text-upper">Premint</span> Collector Pass</h2>
                <p>Be one of 10,000 people to get access to the collector side of web3's most popular access list platform. See below for holder benefits, roadmap and mint schedule.</p>

                <button class="btn btn-default btn-lg w-100 text-upper mt-2">
                    Buy On OpenSea
                </button>

                <div class="card bg-dark text-white p-3 mt-3">
                    <p><b>Mint sold out!</b></p>
                    <p><small>Thanks to everyone for become a PREMINT Collector Pass holder! Looking for a pass? Check out secondary listings on OpenSea!</small></p>

                    <b-progress :value="progress.value" :max="progress.max" variant="success" animated></b-progress>

                    <p class="mb-0">
                        <small>
                            {{progress.max - progress.value}} / {{progress.max}} supply remaining
                        </small>
                    </p>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PassDesign',
  data() {
      return {
          progress: {
              value: 333,
              max: 333,
          }
      }
  },
}
</script>
