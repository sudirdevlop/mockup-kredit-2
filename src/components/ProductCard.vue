<template>
  <div class="bg-white rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 overflow-hidden">
    <!-- Badge -->
    <div class="bg-gradient-to-r from-primary-500 to-primary-600 text-white px-4 py-2 text-sm font-semibold">
      {{ product.highlight }}
    </div>
    
    <div class="p-6">
      <!-- Header -->
      <div class="flex items-start justify-between mb-4">
        <div class="flex items-center">
          <span class="text-4xl mr-3">{{ product.logo }}</span>
          <div>
            <h3 class="font-bold text-lg text-gray-900">{{ product.name }}</h3>
            <p class="text-sm text-gray-600">{{ product.bank }}</p>
          </div>
        </div>
      </div>

      <!-- Rating -->
      <div class="flex items-center mb-4">
        <div class="flex text-yellow-400 mr-2">
          <span v-for="i in 5" :key="i">
            {{ i <= Math.floor(product.rating) ? '★' : '☆' }}
          </span>
        </div>
        <span class="text-sm font-semibold text-gray-700">{{ product.rating }}</span>
      </div>

      <!-- Features -->
      <div class="mb-6">
        <ul class="space-y-2">
          <li v-for="(feature, index) in product.features" :key="index" class="flex items-start text-sm text-gray-700">
            <svg class="w-5 h-5 text-success-500 mr-2 flex-shrink-0 mt-0.5" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            {{ feature }}
          </li>
        </ul>
      </div>

      <!-- Actions -->
      <div class="flex gap-2">
        <button class="flex-1 bg-primary-600 text-white px-4 py-3 rounded-lg hover:bg-primary-700 transition-colors font-semibold">
          Lihat Detail
        </button>
        <button class="px-4 py-3 border-2 border-primary-600 text-primary-600 rounded-lg hover:bg-primary-50 transition-colors">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    product: {
      type: Object,
      required: true
    }
  }
}
</script>
