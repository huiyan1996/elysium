<template>
  <div class="container mt-5" id="faq">
      <h1 class="text-center text-white"><b>FAQ</b></h1>

      <div class="accordionWrapper" v-for="(v, k) in displayList" :key="k">
            <button type="button" class="accordionTitle" :class="{open: v.isShow}" @click="v.isShow = !v.isShow">
                <div class="titleWidth">
                    <span>{{v.title}}</span>
                    <b-icon class="icon" :icon="v.isShow?'dash-lg':'plus-lg'"></b-icon>
                </div>
            </button>
            <b-collapse v-model="v.isShow">
                <div class="accordionContent" v-html="v.content"></div>
            </b-collapse>
        </div>
  </div>
</template>

<script>
export default {
  name: 'Faq',
  data() {
      return {
          displayList: [
              {
                  title: "What is PlayOS SPACE GENESIS?",
                  content: "Our mission is to create and support world-changing projects and movements that combine WEB2.0 and WEB3.0 utilities. Our team is ready to push the boundary of what is possible in Web3 World and Web2 with the communities. we believe there must be a bridge and a balance between web2.0 and 3.0",
                  isShow: false,
              },
              {
                  title: "What are the utilities for PlayOS?",
                  content: "PlayOS Space Pass is an community membership pass that allows you to guaranteed a free airdrop for our upcoming next 3 NFT project & WL for upcoming all projects released by PlayOS or partners. Our next direction was to build an Exclusive Hub, which allow our holder gain access to playos space with VIP guests.<br>A community own space , bridging web2 to web3. ",
                  isShow: false,
              },
              {
                  title: "How many PLAYOS Space Genesis will be available?",
                  content: "Limited 333 Piece only",
                  isShow: false,
              },
            //   {
            //       title: "What is the mint date and price?  ",
            //       content: "Our mint date will be at 10 Jun 2022 with mint price of 0.4 ETH",
            //       isShow: false,
            //   },
              {
                  title: "Where can I mint a PLAYOS Space Genesis ?  ",
                  content: "Every WL will be able to mint a Genesis from our website that will be released when the mint phase begins. The details will be on our Twitter.",
                  isShow: false,
              },
              {
                  title: "Which marketplaces will PLAYOS Space Genesis be listed on?",
                  content: "Opensea",
                  isShow: false,
              },
              {
                  title: "Where else can I buy a PLAYOS Space Genesis NFT if I unable to mint? ",
                  content: "PLAYOS Space Genesis will also be available to purchase on secondary marketplaces such as OpenSea Please check back on our website for the links to our official collection on each secondary exchange.",
                  isShow: false,
              },
          ],
      }
  },
}
</script>

<style lang="scss">
$themeLight: #72c7b7;
$themeMiddle: #112639;
$themeDark: #17152a;

.accordionWrapper {
    margin-top: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid #333;

    .accordionTitle {
        background: $themeDark;
        color: #fff;
        border: none;
        width: 100%;
        padding: 15px;
        text-align: left;
        font-weight: bold;
        transition: .3s;

        .titleWidth {
            display: flex;
            width: 85%;
            margin: 0 auto;
            justify-content: space-between;
            align-items: center;

            .icon {
                font-size: 15px;
            }
        }

        &.open {
            background: rgba(255,255,255,.2);
            color: #fff;
        }
    }

    .accordionContent {
        padding: 40px 7.5%;
        box-shadow: 0 0 15px -10px #000;
        transition: .3s;
        color: #fff;
    }
}
</style>