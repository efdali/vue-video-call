<template>
  <main>
    <Phone />
  </main>
</template>

<script>
import Phone from '@/components/Phone.vue';

export default {
  name: 'App',
  components: {
    Phone,
  },
};
</script>

<style lang="scss">
main {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
