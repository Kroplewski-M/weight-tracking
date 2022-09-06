<template>
  <div class="w-[99vw] h-[100vh] bg-[#111111]">
    <AppWelcome></AppWelcome>
    <div class="w-[800px] mx-auto">
      <AppOverview></AppOverview>
      <AppWeightTracker></AppWeightTracker>
  </div>
  </div>
</template>

<script>
  import AppWeightTracker from '@/components/AppWeightTracker.vue'
  import AppWelcome from '@/components/AppWelcome.vue'
  import AppOverview from '@/components/AppOverview.vue'

  export default{
    name:"App",
    components: {
    AppWelcome,
    AppWeightTracker,
    AppOverview,
}
  }


</script>

