<template>
  <div id="app" class="font-sans text-lg leading-normal min-h-screen py-8 bg-grey-light text-grey-darkest">
    <TipCalculator />
  </div>
</template>

<script>
import TipCalculator from './components/TipCalculator';

export default {
  components: { TipCalculator },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box !important;
}
</style>
