<!-- components/YezBadge.vue -->
<template>
  <a :href="url" target="_blank" rel="noopener noreferrer" :class="`VPBadge ${type}`"
     style="text-decoration: none; color: inherit;">
    {{ text }}
    <svg width="20px" height="20px" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g id="Interface / Download">
        <path id="Vector" d="M6 21H18M12 3V17M12 17L17 12M12 17L7 12" stroke="var(--svg-color)" stroke-width="2"
              stroke-linecap="round" stroke-linejoin="round" />
      </g>
    </svg>
  </a>
</template>

<script setup>
defineProps({
  type: String,
  text: String,
  url: {
    type: String,
    required: true
  }
})
</script>
<style scoped>
.VPBadge.keenetic {
  --svg-color: white;
  transform: translateY(0px);
  display: flex;
  color: white !important;
  align-items: center;
  gap: 10px;
  transition: 0.1s linear;
}

.VPBadge.keenetic:hover {
  --svg-color: #0f98d9;
  background-color: white;
  color: #0f98d9 !important;
  transition: 0.1s linear;
}
</style>
