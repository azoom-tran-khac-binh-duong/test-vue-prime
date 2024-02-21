<script setup lang="ts">
const checked = ref(true)
</script>
<template>
  <InputSwitch
    v-model="checked"
    :pt="{
      slider: ({ props }) => ({
        class: props.modelValue ? 'my-custom-slider -checked' : 'my-custom-slider -unchecked',
      }),
      input: 'my-custom-input',
      root: 'my-custom-root',
    }"
  />
</template>
<style>
.my-custom-slider {
  font-size: 8px;
  transition: ease-in-out 0.5s;
  color: white;
}

.my-custom-slider.-unchecked::after {
  content: 'OFF';
  position: absolute;
  top: 8px;
  right: 0;
  margin: 0 4px;
}

.my-custom-slider.-checked::after {
  content: 'ON';
  position: absolute;
  top: 8px;
  margin: 0 4px;
}
</style>
