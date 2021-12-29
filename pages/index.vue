<template>
  <test>
    <template v-slot:header>
      <h1>Here might be a page title</h1>
    </template>

    <template v-slot:default>
      <p>A paragraph for the main content.</p>
      <p>And another one.</p>
    </template>

    <template v-slot:footer>
      <p>Here's some contact info</p>
    </template>
  </test>  
</template>

<script>
import test from '@/components/test.vue'

export default {
  components: {
    test
  }
}
</script>