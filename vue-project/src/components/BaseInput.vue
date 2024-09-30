<template>
    <div class="input-wrapper">
    <slot></slot>
  
      <input
        :type="type"
        :placeholder="placeholder"
        
      />
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    placeholder: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text', 
    },
  });
  
  const emit = defineEmits(['update:modelValue']);
  
  const onInput = (event) => {
    emit('update:modelValue', event.target.value);
  };
  </script>
  
  <style scoped>
  .input-wrapper {
    display: flex;
    align-items: center;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 8px;
  }
  
  input {
    border: none;
    outline: none;
    flex: 1;
    padding: 8px;
    font-size: 16px;
  }
  
  ::placeholder {
    color: #999;
  }
  
  .slot-icon {
    margin-right: 8px;
  }
  </style>
  