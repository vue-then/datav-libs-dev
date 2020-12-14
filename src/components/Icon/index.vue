<template>
  <svg>
    <use :href="iconName" :style="{...styles}"></use>
  </svg>
</template>

<script>
  export default {
    name: 'Icon',
    props: {
      name: {
        type: String,
      },
      styles: {
        type: Object
      },
      prefix: {
        type: String
      }
    },
    setup(ctx) {
      const iconName = computed(() => {
        if (ctx.prefix) {
          return `#${ctx.prefix}${ctx.name}`
        } else {
          return `#${ctx.name}`
        }
      })

      return {
        iconName
      }
    }

  }
</script>

<style>

</style>