<template>
  <div class="onboard-sublocation">
    <div class="onboard-carrier">
      <transition name="fade" appear>
        <a-markdown class="onboard-markdown" :content="content"></a-markdown>
      </transition>
      <div class="continue-box">
        <router-link class="button is-outlined next-button" to="/onboard/3">
          CONTINUE
        </router-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  export default {
    name: 'onboard2',
    data() {
      return {
        content: textContent
      }
    }
  }
  var textContent = `
## Aether is ephemeral

Things you post will eventually disappear. Think of it like Snapchat. You can post text, GIFs, videos, and images.

We care about privacy here. Deleted data can't leak.
  `
</script>

<style lang="scss" scoped>
  @import"../../../scss/bulmastyles";
  @import"../../../scss/globals";
  // .onboard-sublocation {
  //   display: flex;
  //   flex: 1;
  //   min-height: 100%;
  //   .onboard-carrier {
  //     margin: auto;
  //     display: flex;
  //     width: 518px;
  //     flex-direction: column;
  //     position: relative;
  //     bottom: 5%;
  //   }
  // }

  .continue-box {
    display: flex;
    margin-top: 15px;
    .next-button {
      @extend %link-hover-ghost-extenders-disable;
      background-color: $a-transparent;
      color: $a-grey-800;
      &:hover {
        background-color: $a-grey-800;
        color: $mid-base;
      }
      animation-duration: 1s;
      animation-name: DELAY_VISIBLE;
    }
  }

  @keyframes DELAY_VISIBLE {
    0% {
      opacity: 0;
    }
    60% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  .fade-enter-active,
  .fade-leave-active {
    transition-property: opacity;
    transition-duration: .25s;
  }

  .fade-enter-active {
    transition-delay: .25s;
  }

  .fade-enter,
  .fade-leave-active {
    opacity: 0
  }
</style>

<style lang="scss">
  .onboard-markdown {
    font-size: 120%;
    p {
      font-family: "SSP Regular"
    }
  }
</style>