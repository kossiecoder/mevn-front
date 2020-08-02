<template>
  <small class="text-danger">{{ errors[0] }}</small>
</template>

<script>
export default {
    props: {
        errors: {
            type: Array,
            required: true
        }
    }
}
</script>

<style>

</style>    