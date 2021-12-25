<template>
  <main-layout>
    <h2>Gissele</h2>
    <slot/>
  </main-layout>
</template>

<script>
import MainLayout from '@/layouts/MainLayout'

export default {
  name: 'App',
  components: {
    MainLayout
  }
}
</script>

<style>
</style>
