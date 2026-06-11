<template>
  <div
    class="overflow-hidden bg-white border border-gray-100 shadow-xl rounded-2xl transition-all duration-300 hover:shadow-2xl"
  >
    <div class="relative h-32 bg-gradient-to-r from-blue-500 to-indigo-600">
      <div class="absolute -bottom-12 left-6">
        <img
          :src="photo"
          :alt="name"
          class="w-24 h-24 object-cover rounded-xl border-4 border-white shadow-md bg-gray-50"
        />
      </div>
    </div>

    <div class="pt-14 p-6">
      <span class="text-xs font-semibold uppercase tracking-wider text-indigo-600">{{
        title
      }}</span>

      <h1 class="mt-1 text-2xl font-bold text-gray-900 tracking-tight">{{ name }}</h1>

      <p class="mt-3 text-sm leading-relaxed text-gray-500">{{ description }}</p>
      <p class="mt-3 text-sm leading-relaxed text-gray-500">{{ position }}</p>

      <div class="flex justify-between">
        <div class="mt-6 pt-4 border-t border-gray-100 flex justify-end">
          <button
            class="px-4 py-2 text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 active:bg-indigo-800 rounded-lg shadow-sm transition-colors duration-200"
          >
            View Profile
          </button>
        </div>
        <div class="mt-6 pt-4 border-t border-gray-100 flex justify-end">
          <button
            @click="handleDelete"
            class="px-4 py-2 text-sm font-medium text-white bg-red-600 hover:bg-red-700 active:bg-red-800 rounded-lg shadow-sm transition-colors duration-200"
          >
            Delete
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  title: String,
  description: String,
  photo: String,
  position: Number,
})

const emit = defineEmits(['deleteItem'])

const handleDelete = () => {
  emit('deleteItem', props.position)
}
</script>

<style lang="scss" scoped></style>
