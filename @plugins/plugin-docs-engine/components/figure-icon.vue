<template>
  <svg
    class="docs-figure-icon"
    xmlns="http://www.w3.org/2000/svg"
    height="24"
    viewBox="0 0 24 24"
    width="24"
    :class="color"
  >
    <template v-if="icon == 'search'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M11.49 16c.88 0 1.7-.26 2.39-.7l2.44 2.44 1.42-1.42-2.44-2.43c.44-.7.7-1.51.7-2.39C16 9.01 13.99 7 11.5 7S7 9.01 7 11.5 9.01 16 11.49 16zm.01-7c1.38 0 2.5 1.12 2.5 2.5S12.88 14 11.5 14 9 12.88 9 11.5 10.12 9 11.5 9zM20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 14H4V6h16v12z"
      />
    </template>
    <template v-else-if="icon == 'doc'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M8 16h8v2H8zm0-4h8v2H8zm6-10H6c-1.1 0-2 .9-2 2v16c0 1.1.89 2 1.99 2H18c1.1 0 2-.9 2-2V8l-6-6zm4 18H6V4h7v5h5v11z"
      />
    </template>
    <template v-else-if="icon == 'apps'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M16.66 4.52l2.83 2.83-2.83 2.83-2.83-2.83 2.83-2.83M9 5v4H5V5h4m10 10v4h-4v-4h4M9 15v4H5v-4h4m7.66-13.31L11 7.34 16.66 13l5.66-5.66-5.66-5.65zM11 3H3v8h8V3zm10 10h-8v8h8v-8zm-10 0H3v8h8v-8z"
      />
    </template>
    <template v-else-if="icon == 'touch'">
      <g>
        <rect fill="none" height="24" width="24" />
      </g>
      <g>
        <g>
          <path
            class="filler"
            d="M18.19,12.44l-3.24-1.62c1.29-1,2.12-2.56,2.12-4.32c0-3.03-2.47-5.5-5.5-5.5s-5.5,2.47-5.5,5.5c0,2.13,1.22,3.98,3,4.89 v3.26c-2.15-0.46-2.02-0.44-2.26-0.44c-0.53,0-1.03,0.21-1.41,0.59L4,16.22l5.09,5.09C9.52,21.75,10.12,22,10.74,22h6.3 c0.98,0,1.81-0.7,1.97-1.67l0.8-4.71C20.03,14.32,19.38,13.04,18.19,12.44z M17.84,15.29L17.04,20h-6.3 c-0.09,0-0.17-0.04-0.24-0.1l-3.68-3.68l4.25,0.89V6.5c0-0.28,0.22-0.5,0.5-0.5c0.28,0,0.5,0.22,0.5,0.5v6h1.76l3.46,1.73 C17.69,14.43,17.91,14.86,17.84,15.29z M8.07,6.5c0-1.93,1.57-3.5,3.5-3.5s3.5,1.57,3.5,3.5c0,0.95-0.38,1.81-1,2.44V6.5 c0-1.38-1.12-2.5-2.5-2.5c-1.38,0-2.5,1.12-2.5,2.5v2.44C8.45,8.31,8.07,7.45,8.07,6.5z"
          />
        </g>
      </g>
    </template>
    <template v-else-if="icon == 'user'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M12 6c1.1 0 2 .9 2 2s-.9 2-2 2-2-.9-2-2 .9-2 2-2m0 9c2.7 0 5.8 1.29 6 2v1H6v-.99c.2-.72 3.3-2.01 6-2.01m0-11C9.79 4 8 5.79 8 8s1.79 4 4 4 4-1.79 4-4-1.79-4-4-4zm0 9c-2.67 0-8 1.34-8 4v3h16v-3c0-2.66-5.33-4-8-4z"
      />
    </template>
    <template v-else-if="icon == 'email'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6zm-2 0l-8 5-8-5h16zm0 12H4V8l8 5 8-5v10z"
      />
    </template>
    <template v-else-if="icon == 'settings'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M19.43 12.98c.04-.32.07-.64.07-.98 0-.34-.03-.66-.07-.98l2.11-1.65c.19-.15.24-.42.12-.64l-2-3.46c-.09-.16-.26-.25-.44-.25-.06 0-.12.01-.17.03l-2.49 1c-.52-.4-1.08-.73-1.69-.98l-.38-2.65C14.46 2.18 14.25 2 14 2h-4c-.25 0-.46.18-.49.42l-.38 2.65c-.61.25-1.17.59-1.69.98l-2.49-1c-.06-.02-.12-.03-.18-.03-.17 0-.34.09-.43.25l-2 3.46c-.13.22-.07.49.12.64l2.11 1.65c-.04.32-.07.65-.07.98 0 .33.03.66.07.98l-2.11 1.65c-.19.15-.24.42-.12.64l2 3.46c.09.16.26.25.44.25.06 0 .12-.01.17-.03l2.49-1c.52.4 1.08.73 1.69.98l.38 2.65c.03.24.24.42.49.42h4c.25 0 .46-.18.49-.42l.38-2.65c.61-.25 1.17-.59 1.69-.98l2.49 1c.06.02.12.03.18.03.17 0 .34-.09.43-.25l2-3.46c.12-.22.07-.49-.12-.64l-2.11-1.65zm-1.98-1.71c.04.31.05.52.05.73 0 .21-.02.43-.05.73l-.14 1.13.89.7 1.08.84-.7 1.21-1.27-.51-1.04-.42-.9.68c-.43.32-.84.56-1.25.73l-1.06.43-.16 1.13-.2 1.35h-1.4l-.19-1.35-.16-1.13-1.06-.43c-.43-.18-.83-.41-1.23-.71l-.91-.7-1.06.43-1.27.51-.7-1.21 1.08-.84.89-.7-.14-1.13c-.03-.31-.05-.54-.05-.74s.02-.43.05-.73l.14-1.13-.89-.7-1.08-.84.7-1.21 1.27.51 1.04.42.9-.68c.43-.32.84-.56 1.25-.73l1.06-.43.16-1.13.2-1.35h1.39l.19 1.35.16 1.13 1.06.43c.43.18.83.41 1.23.71l.91.7 1.06-.43 1.27-.51.7 1.21-1.07.85-.89.7.14 1.13zM12 8c-2.21 0-4 1.79-4 4s1.79 4 4 4 4-1.79 4-4-1.79-4-4-4zm0 6c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2z"
      />
    </template>
    <template v-else-if="icon == 'layout'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M4 5v13h17V5H4zm2 11V7h3v9H6zm5 0v-3.5h3V16h-3zm8 0h-3v-3.5h3V16zm-8-5.5V7h8v3.5h-8z"
      />
    </template>
    <template v-else-if="icon == 'image'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M19 5v14H5V5h14m0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-4.86 8.86l-3 3.87L9 13.14 6 17h12l-3.86-5.14z"
      />
    </template>
    <template v-else-if="icon == 'bold'">
      <path d="M0 0h24v24H0z" fill="none" />
      <path
        class="filler"
        d="M12 2.02c-5.51 0-9.98 4.47-9.98 9.98s4.47 9.98 9.98 9.98 9.98-4.47 9.98-9.98S17.51 2.02 12 2.02zm0 17.96c-4.4 0-7.98-3.58-7.98-7.98S7.6 4.02 12 4.02 19.98 7.6 19.98 12 16.4 19.98 12 19.98zM12.75 5l-4.5 8.5h3.14V19l4.36-8.5h-3z"
      />
    </template>
    <template v-else-if="icon == 'quick'">
      <path d="M0 0h24v24H0z" fill="none" />
      <path
        class="filler"
        d="M12 2.02c-5.51 0-9.98 4.47-9.98 9.98s4.47 9.98 9.98 9.98 9.98-4.47 9.98-9.98S17.51 2.02 12 2.02zm0 17.96c-4.4 0-7.98-3.58-7.98-7.98S7.6 4.02 12 4.02 19.98 7.6 19.98 12 16.4 19.98 12 19.98zM12.75 5l-4.5 8.5h3.14V19l4.36-8.5h-3z"
      />
    </template>
    <template v-else-if="icon == 'example'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M3.55 19.09l1.41 1.41 1.79-1.8-1.41-1.41zM11 20h2v3h-2zM1 11h3v2H1zm12-6.95v3.96l1 .58c1.24.72 2 2.04 2 3.46 0 2.21-1.79 4-4 4s-4-1.79-4-4c0-1.42.77-2.74 2-3.46l1-.58V4.05h2m2-2H9v4.81C7.21 7.9 6 9.83 6 12.05c0 3.31 2.69 6 6 6s6-2.69 6-6c0-2.22-1.21-4.15-3-5.19V2.05zM20 11h3v2h-3zm-2.76 7.71l1.79 1.8 1.41-1.41-1.8-1.79z"
      />
    </template>

    <template v-else-if="icon == 'plugin'">
      <path d="M0 0h24v24H0V0z" fill="none" />
      <path
        class="filler"
        d="M16 9v4.66l-3.5 3.51V19h-1v-1.83L8 13.65V9h8m0-6h-2v4h-4V3H8v4h-.01C6.9 6.99 6 7.89 6 8.98v5.52L9.5 18v3h5v-3l3.5-3.51V9c0-1.1-.9-2-2-2V3z"
      />
    </template>
  </svg>
</template>

<script lang="ts">
import Vue from "vue"

export default Vue.extend({
  components: {},
  props: {
    icon: { type: String, default: "" },
    color: { type: String, default: "text" }
  }
})
</script>

<style lang="less">
.docs-figure-icon {
  .filler {
    fill: var(--color-text);
  }
  &.white {
    .filler {
      fill: #fff;
    }
  }
  &.primary {
    .filler {
      fill: var(--color-primary);
    }
  }
  &.tertiary {
    .filler {
      fill: #8d68ce;
    }
  }
  &.purple {
    .filler {
      fill: #3d0c85;
    }
  }
}
</style>
