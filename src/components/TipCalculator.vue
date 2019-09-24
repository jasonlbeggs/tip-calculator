<template>
  <div class="flex flex-col items-center justify-center container mx-auto px-4">
    <div class="w-full lg:w-1/2 mb-6 bg-white rounded-lg shadow">
      <h1 class="py-4 px-6 rounded-t-lg text-2xl">
        Tip Calulator
      </h1>
      <div class="pt-2 pb-6 px-6">
        <div class="sm:flex items-center mb-4 sm:mb-8">
          <div class="mb-4 sm:mr-8 flex-1">
            <label
              for="cost"
              class="block mb-1 uppercase text-base tracking-wide font-semibold text-gray-700"
              >Initial Cost:</label
            >
            <div
              class="relative cost bg-gray-200 rounded-lg border-2 border-gray-300"
            >
              <input
                id="cost"
                v-model.number="cost"
                class="w-full py-3 pl-8 pr-4 bg-gray-200 rounded-lg focus:outline-none focus:shadow-outline"
                type="text"
                autofocus
              />
            </div>
          </div>
          <div class="mb-4 sm:mr-8 flex-1">
            <label
              for="percentage"
              class="block mb-1 uppercase text-base tracking-wide font-semibold text-gray-700"
              >Tip Percentage:</label
            >
            <div
              class="relative percentage bg-gray-200 rounded-lg border-2 border-gray-300"
            >
              <input
                id="percentage"
                v-model.number="percent"
                class="w-full py-3 px-4 bg-gray-200 rounded-lg focus:outline-none focus:shadow-outline"
                type="text"
              />
            </div>
          </div>
        </div>
        <div class="sm:flex items-center">
          <div class="flex items-center mb-4 mr-8 flex-1">
            <span
              class="uppercase text-base tracking-wide font-semibold text-gray-700 mr-2"
              >Tip Amount:</span
            >
            <span class="text-teal-600">${{ tip }}</span>
          </div>
          <div class="flex items-center sm:mb-4 mr-8 flex-1">
            <span
              class="uppercase text-base tracking-wide font-semibold text-gray-700 mr-2"
              >Total Cost:</span
            >
            <span class="text-teal-600">${{ total }}</span>
          </div>
        </div>
      </div>
    </div>
    <div class="text-center">
      <a
        href="https://jasonlbeggs.com"
        class="text-gray-600 no-underline rounded p-1 focus:outline-none focus:shadow-outline"
        >Made with &hearts; by jasonlbeggs</a
      >
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      percent: 20,
      cost: 25,
    };
  },
  computed: {
    tip() {
      return ((this.cost * this.percent) / 100).toFixed(2);
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
