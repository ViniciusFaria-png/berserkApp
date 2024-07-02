<template>
  <div class="game">
      <BehelitSection />
      <MiddleSection />
      <UpgradeSection />
  </div>
</template>

<script>
  import BehelitSection from 'src/components/BehelitSection.vue'
  import MiddleSection from 'src/components/MiddleSection.vue'
  import UpgradeSection from 'src/components/UpgradeSection.vue'

  export default {
      components: {
        BehelitSection,
        MiddleSection,
        UpgradeSection
      }
  }
</script>

<style scoped>
  .game {
      height: 100%;
      background: white;
      display: flex;
  }
</style>
