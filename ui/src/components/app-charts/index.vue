<template>
  <component
    :is="typeComponentMap[type]"
    :height="height"
    :option="option"
    :dataZoom="dataZoom"
    class="v-charts"
  />
</template>
<script lang="ts" setup>
import line from './components/LineCharts.vue'
defineOptions({ name: 'AppCharts' })
defineProps({
  type: {
    type: String,
    default: 'line'
  },
  height: {
    type: String,
    default: '200px'
  },
  dataZoom: Boolean,
  option: {
    type: Object,
    required: true
  } // { title , xDatas, yDatas, formatStr  }
})

const typeComponentMap = { line } as any
</script>
