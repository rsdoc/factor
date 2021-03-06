<template>
  <div class="site-head">
    <div class="site-head-pad">
      <div class="mob-nav-btn" @click.stop>
        <div class="toggle" :class="{ active: toggle }" @click="toggleNav()" />
      </div>
      <div class="brand">
        <factor-link path="/">
          <site-logo />
        </factor-link>
      </div>
      <transition name="fade">
        <div v-if="toggle" class="overlay" :class="{ open: toggle }" />
      </transition>
      <div class="nav" :class="{ open: toggle }">
        <factor-link class="mobile-logo" path="/">
          <site-logo />
        </factor-link>
        <slot />
        <account-menu v-if="userId()" />
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { accountMenu } from "@factor/plugin-standard-signin"
import { factorLink } from "@factor/ui"
import { userId } from "@factor/user"
import Vue from "vue"
export default Vue.extend({
  components: {
    accountMenu,
    factorLink,
    "site-logo": () => import("./logo.vue")
  },
  data() {
    return {
      toggle: false
    }
  },
  methods: {
    userId,
    toggleNav(v) {
      if (typeof v == "undefined") {
        this.toggle = !this.toggle
      } else {
        this.toggle = v
      }

      this.clickHandler = () => {
        this.toggle = false

        document.removeEventListener("click", this.clickHandler)
      }

      if (this.toggle) {
        document.addEventListener("click", this.clickHandler)
      } else {
        document.removeEventListener("click", this.clickHandler)
      }
    }
  }
})
</script>
<style lang="less">
.site-head {
  padding: 1rem 1rem;
  width: 100%;
  position: fixed;
  z-index: 110;
  @media (max-width: 900px) {
    padding: 0 0.5em;
  }
  transition: all 0.3s;
  will-change: padding;
}
.factor-site {
  .site-head {
    opacity: 0;
  }
  &.scrolled,
  &.top {
    .site-head {
      opacity: 1;
    }
  }
  &.scrolled {
    .site-head {
      padding: 0rem 1rem;
      background: #fff;
      box-shadow: 0 1px 1px rgba(0, 0, 0, 0.1);
    }
  }
}

.site-head-pad {
  max-width: var(--max-width);
  padding: 0 1.5rem;
  margin: 0 auto;
  width: 100%;

  height: 45px;
  align-items: center;
  display: flex;
  justify-content: space-between;

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0;
  }
  .mobile-logo {
    display: none;
  }
  @media (max-width: 900px) {
    flex-direction: column;
    justify-content: center;
    .mobile-logo {
      display: block;
    }
  }
  .overlay {
    display: none;
    height: 100vh;
    width: 100vw;
    background: rgba(0, 0, 0, 0.1);
    z-index: 10;
    position: fixed;
    top: 0;
    cursor: pointer;
    &.open {
      display: block;
    }
  }
  .mob-nav-btn {
    display: none;
    cursor: pointer;

    .toggle {
      cursor: pointer;
      position: relative;
      display: block;
      width: 30px;
      height: 30px;
      &:before,
      &:after {
        content: "";
        position: absolute;
        height: 3px;
        width: 100%;
        left: 0;
        top: 50%;
        margin-top: -1px;
        background-color: var(--color-text);
        transition: 0.29s cubic-bezier(0.52, 0.01, 0.16, 1);
      }
      &:before {
        transform: rotate(0deg) translateY(-5px);
      }
      &:after {
        transform: rotate(0deg) translateY(5px);
      }
    }
    @media (max-width: 900px) {
      position: absolute;
      right: 1em;
      top: 0.5em;
      z-index: 20;
      display: block;
      a.active {
        &:before,
        &:after {
          background-color: var(--color-text);
        }
        &:before {
          transform: rotate(45deg) translateY(0);
        }
        &:after {
          transform: rotate(-45deg) translateY(0);
        }
      }
    }
  }

  .brand {
    display: flex;
    flex-grow: 1;
    align-items: center;
    .search {
      border-radius: 4px;
      flex-grow: 1;
      max-width: 600px;
      padding: 4px 1em;
      color: rgba(38, 67, 89, 0.4);

      background: #f3f5fa;
      margin: 0 2em;
      font-size: 0.9em;
      line-height: 1.6;
    }
  }
  .nav {
    font-weight: var(--font-weight-bold);
    display: flex;
    align-items: center;
    @media (max-width: 900px) {
      // flex-grow: 2;
      // justify-content: flex-end;
      position: fixed;
      display: none;
      z-index: 100;
      height: 100vh;
      top: 0;
      left: 0;
      width: 70%;
      transform: translate(-100%, 0);
      background: #f6f9fc;
      transition: all 0.4s cubic-bezier(0.4, 0, 0, 1);
      &.open {
        display: block;
        transform: translate(0, 0);
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
      }
    }
    > .factor-link {
      letter-spacing: -0.03em;
      font-size: 0.9em;
      color: #3a4854;
      margin: 0 1em;
      @media (max-width: 900px) {
        display: block;
        text-align: left;
        font-size: 1.2em;
        padding: 0.75em;
        margin: 0;
        box-shadow: var(--box-shadow-input);
        background: #fff;
      }
      &:hover,
      &.active {
        color: #0496ff;
      }
      &:active {
        color: #ff0076;
      }
    }
    .account-menu {
      margin-left: 1em;
      // .avatar {
      //   background-color: rgba(38, 67, 89, 0.06);
      // }
      @media (max-width: 900px) {
        display: none;
      }
    }
    // > a,
    // .nav-dropdown {
    //   margin-left: 0.5em;
    // }
    .nav-dropdown-toggle {
      padding: 4px 6px;
      font-weight: 500;
      border-radius: 4px;
      &.active,
      &:hover {
        opacity: 0.6;
      }
    }
  }
}
</style>
