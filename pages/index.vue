<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <Banner />
        <Video />
        <PassDesign />
        <RoadMap />
        <Hub />
        <TokenDistribution />
        <Faq />
      </div>
    </div>

    <div class="row">
      <div class="col-12 footer text-center">
        PlayOS {{new Date().getFullYear()}} &copy; All rights reserved.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
