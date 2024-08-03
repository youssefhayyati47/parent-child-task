<script setup>
const parentArray = ref([]);
const item = ref("");

const add = () => {
  parentArray.value.push(item.value);
  item.value = "";
};
</script>

<template>
  <div class="flex gap-4">
    <div class="bg-red-500 size-[300px] flex flex-col justify-center p-4">
      {{ parentArray }}
      <div class="flex items-end">
        <input type="text" v-model="item" @keyup.enter="add" />
        <button
          @click="add"
          class="bg-green-500 px-2 py-1 ml-4 rounded-lg text-sm text-white"
        >
          Add P
        </button>
      </div>
    </div>
    <Child :parentArray="parentArray" />
  </div>
</template>

<style></style>
