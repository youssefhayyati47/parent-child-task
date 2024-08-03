<script setup>
const props = defineProps(["parentArray"]);
const parentArray = ref(props.parentArray);
const item = ref();
const emit = defineEmits(["update:parentArray"]);

const add = () => {
  parentArray.value.push(item.value);
  emit("update:parentArray", parentArray.value);
  item.value = null;
};
</script>

<template>
  <div class="bg-green-500 size-[300px] flex flex-col justify-center p-4">
    {{ parentArray }}
    <div>
      <input type="text" v-model="item" @keyup.enter="add" />
      <button
        @click="add"
        class="bg-red-500 px-2 py-1 ml-4 rounded-lg text-sm text-white"
      >
        Add C
      </button>
    </div>
  </div>
</template>

<style></style>
