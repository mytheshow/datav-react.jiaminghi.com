<template>
  <div class="for-digital-flop">
    <dv-digital-flop :config="currentConfig" style="width:100%;height:100%;" />
  </div>
</template>

<script>
export default {
  name: 'ForDigitalFlop',
  props: ['data'],
  data() {
    return {
      currentConfig: {},
    }
  },
  mounted() {
    const { data } = this

    this.currentConfig = data[0]
  },
}
</script>
