<template>
    <SectionBalance></SectionBalance>
    <SectionSupport></SectionSupport>
</template>
<script>
import SectionBalance from "@/components/SectionBalance";
import SectionSupport from "@/components/SectionSupport";
export default {
  name: 'App',
  components: {
    SectionSupport,
    SectionBalance,
  },
}
</script>

<style lang="scss">
body {
  background-color: #F5F5F5;
}
body {
  overflow-x: hidden;
}
</style>
