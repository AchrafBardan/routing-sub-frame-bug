<template>
  <Page>
    <ActionBar>
      <Label text="Home"/>
    </ActionBar>

    <StackLayout>
      <Button text="first" @tap="goFirst" />
      <Button text="first no history" @tap="goFirstNoHistory" />
      <Button text="second" @tap="goSecond" />
      <Frame id="subFrame" >
        <Page>

        </Page>
      </Frame>

    </StackLayout>
  </Page>
</template>

<script lang="ts">
  import Vue from "nativescript-vue";
import First from "./First.vue";
import Second from "./Second.vue";

  export default Vue.extend({
    methods: {
      goFirst() {
        this.$navigateTo(First, {
          clearHistory: false,
          frame: 'subFrame'
        });
      },
      goFirstNoHistory() {
        this.$navigateTo(First, {
          clearHistory: true,
          frame: 'subFrame'
        });
      },
      goSecond() {
        this.$navigateTo(Second, {
          clearHistory: false,
          frame: 'subFrame'
        });
      },
    },
});
</script>

<style scoped lang="scss">
  @import '@nativescript/theme/scss/variables/blue';

  // Custom styles
  .fas {
    @include colorize($color: accent);
  }

  .info {
    font-size: 20;
    horizontal-align: center;
    vertical-align: center;
  }
</style>
