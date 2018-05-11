<template>
  <div class="flex items-center justify-center container my-8 mx-auto px-4">
    <div class="w-full lg:w-1/2 bg-grey-lighter rounded shadow">
      <h1 class="bg-grey-darkest text-white py-2 px-6 rounded-t font-normal text-2xl">Tip Calulator</h1>
      <div class="py-6 px-6">
        <div class="sm:flex items-center mb-4 sm:mb-8">
          <div class="mb-4 sm:mr-8 flex-1">
            <label for="cost" class="block mb-1 uppercase text-base tracking-wide font-semibold text-grey-darker">Initial Cost:</label>
            <div class="relative cost bg-white shadow rounded">
              <input id="cost" v-model.number="cost" class="w-full py-3 pl-8 pr-4" type="text" autofocus>
            </div>
          </div>
          <div class="mb-4 sm:mr-8 flex-1">
            <label for="percentage" class="block mb-1 uppercase text-base tracking-wide font-semibold text-grey-darker">Tip Percentage:</label>
            <div class="relative percentage bg-white shadow rounded">
              <input id="percentage" v-model.number="percent" class="w-full py-3 px-4" type="text">
            </div>
          </div>
        </div>
        <div class="sm:flex items-center">
          <div class="flex items-center mb-4 mr-8 flex-1">
            <span class="uppercase text-base tracking-wide font-semibold text-grey-darker mr-2">Tip Amount:</span>
            <span>${{ tip }}</span>
          </div>
          <div class="flex items-center sm:mb-4 mr-8 flex-1">
            <span class="uppercase text-base tracking-wide font-semibold text-grey-darker mr-2">Total Cost:</span>
            <span>${{ total }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      percent: 15,
      cost: 0,
    };
  },
  computed: {
    tip() {
      return (this.cost * this.percent / 100).toFixed(2);
    },
    total() {
      return (Number(this.cost) + Number(this.tip)).toFixed(2);
    },
  },
};
</script>

<style>
.cost:before,
.percentage:after {
  display: block;
  position: absolute;
  top: 38%;
  opacity: 0.35;
  margin-top: -9px;
  z-index: 2;
}
.cost:before {
  content: '$';
  left: 12px;
}
.percentage:after {
  content: '%';
  right: 12px;
}
</style>
