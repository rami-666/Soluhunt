<template>
  <div class="earlyDays">
    <TitleSection scene="earlyTitle">
      <TitleFunction params="2011,2018" subtitle="&lt;table&gt;&lt;tr&gt;&lt;td&gt;..."
        >earlyDays</TitleFunction
      >

      <div class="clouds cloud-1"></div>
      <Pepe v-bind="{ isPlaying }" />
      <div class="clouds cloud-2"></div>
      <div class="clouds cloud-3"></div>
      <Ocean v-bind="{ isPlaying }" />
    </TitleSection>

    <Scene id="early-days">
      <TextBlock>
        <p>Mobile and Web</p>
        <p class="-big">
          A frontend developer<br />
          <span class="-purple">with one foothold in arts.</span>
        </p>
      </TextBlock>
    </Scene>
    <Scene id="early-days2">
      <TextBlock>
        <p class="-big">
          <span class="-purple">Consulting</span> &
          <span class="-purple">Advertising,</span><br />
          <span class="-purple">NFT</span> &
          <span class="-purple">Defi</span> projects.
        </p>
        <p>
          Apart from developing web3 projects, we can take them on in a deeper level
          providing our past-experiences and knowledge in the space to handle any project from A-Z.
          A team of investors are also ready to provide consultancy services as well as advertising for any 
          defi or NFT project.
          <br />
        </p>
      </TextBlock>
    </Scene>

  </div>
</template>

<script>
import { Pepe, Ocean } from '../Characters'
import TitleSection from './TitleSection.vue'
import TitleFunction from './TitleFunction.vue'
import TextBlock from '../TextBlock.vue'
import Scene from '../Scene.vue'

export default {
  name: 'EarlyDaysScene',
  components: {
    TitleSection,
    Pepe,
    Ocean,
    TitleFunction,
    TextBlock,
    Scene,
  },
  props: {
    isPlaying: Boolean,
  },
}
</script>

<style lang="scss">
.earlyDays {
  .pepe {
    position: absolute;
    z-index: 2;
    top: 50%;
    left: 100%;
    transform: scale(0.4) translate3d(0, -50%, 0);
    transform-origin: 0 0;

    @media screen and (max-width: 568px) {
      transform: scale(0.2) translate3d(0, -50%, 0);
    }
  }

  .clouds {
    position: absolute;
    width: 150vw;
    height: 150vh;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    transform-origin: 50% 50%;
    background: url('../Characters/Pepe/assets/clouds-1.png') no-repeat center;
    background-size: contain;
    opacity: 0.5;

    &.cloud-2 {
      background-image: url('../Characters/Pepe/assets/clouds-2.png');
    }
    &.cloud-3 {
      background-image: url('../Characters/Pepe/assets/clouds-3.png');
      width: 100vw;
      height: 100vh;
      z-index: -1;
      opacity: 0.25;
    }
  }
}
</style>
