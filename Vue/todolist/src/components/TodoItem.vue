<template>
<li @click="handleDelete">{{content}}</li>
</template>

<script>
export default {
  props: ['comtent', 'index'],
  methods: {
    handleDelete () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<style scoped>

</style>
