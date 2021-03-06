<template>
  <div>
    <HomeHero>
      <h2 class="top-title">Give your NavCoin address a name!</h2>
      <CreateAlias />
    </HomeHero>
    <MemorableSection />
    <InfoSection :containerStyle="{ 'background-color': '#f7f7f7', 'padding': '50px 0' }">
      <template slot="title">Why use OpenAlias?</template>
      <template slot="text">OpenAlias was created by contributors to the Monero Cryptocurrency project who wanted to find a way of simplifying cryptocurrency payments by bridging the knowledge gap between cryptographically secure systems and users who aren't sophisticated developers.</template>
      <template slot="children">
        <Icon src="/images/purple-telegram.png">
          <span slot="title" class="title">Easier</span>
          <span slot="subtext" class="subtext">You can transform long alphanumeric codes into an easily memorisable address.</span>
        </Icon>
        <Icon src="/images/purple-safe.png">
          <span slot="title" class="title">Security</span>
          <span slot="subtext" class="subtext">NavCoin OpenAlias leverages DNSSEC to prevent MITM attacks on the alias.</span>
        </Icon>
        <Icon src="/images/purple-fast.png">
          <span slot="title" class="title">Saves time</span>
          <span slot="subtext" class="subtext">It's quicker to remember a meaningful alias than a long random-looking string.</span>
        </Icon>
      </template>
    </InfoSection>

    <InfoSection>
      <template slot="title">How to create your Alias</template>
      <!-- <template slot="text"><p class="centerText">Follow the three easy steps and you'll be all set!</p></template> -->
      <template slot="children">
        <Icon src="/images/purple-community.png">
          <span slot="title" class="title">1. Register your alias</span>
          <!-- <span slot="text" class="subtext">Register a name you like and the suffix \'@nav.community\' will be added to it.</span> -->
        </Icon>
        <Icon src="/images/purple-message.png">
          <span slot="title" class="title">2. Copy the message to console</span>
          <!-- <span slot="subtext" class="subtext">A line of code will be generated to verify your alias. Follow the instruction to copy it to your console.</span> -->
        </Icon>
        <Icon src="/images/purple-greentick.png">
          <span slot="title" class="title">3. Verify</span>
          <!-- <span slot="subtext" class="subtext">The final step will involve pasting your verification code back into the OpenAlias website.</span> -->
        </Icon>
      </template>
      <template slot="button"><a href="#">Create your Alias</a></template>
    </InfoSection>


    <FooterFull />
  </div>
</template>

<script>
// @ is an alias to /src
import { mapMutations } from "vuex";

import HomeHero from "../components/HomeHero";
import CreateAlias from "../components/CreateAlias";
import MemorableSection from "@/components/MemorableSection.vue";
import InfoSection from "@/components/InfoSection.vue";
import Icon from "@/components/Icon.vue";
import FooterFull from "@/components/FooterFull.vue";

export default {
  name: "Home",
  mounted: function() {
    this.resetStateData();
  },
  methods: {
    ...mapMutations({
      savePrevAddressVerification: "savePrevAddressVerification",
      resetStateData: "resetStateData"
    })
  },
  components: {
    HomeHero,
    CreateAlias,
    MemorableSection,
    InfoSection,
    Icon,
    FooterFull
  }
};
</script>

<style scoped>
h2 {
  color: white;
  margin: 0 0 20px 0;
}

.centerText {
  text-align: center;
}

.top-title{
  font-size:56px;
}

@media (max-width: 600px) {
  .top-title{
    font-size:40px;
    padding: 0 10px 0 10px;
  }
}

.title{
  font-family: 'Raleway', 'Regular', Helvetica, Arial, sans-serif;
  font-size: 21px;
  font-weight: 300;
  margin-top:2%;
}

.subtext{
  width: 80vw;
  max-width: 282px;
  margin-top: 5%;
  font-size:15px;
  line-height: 25px;
  font-weight: 300;
}


</style>
