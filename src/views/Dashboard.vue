<template>
  <div :class="className">
    <h1 :class="`${className}__title`">Picture Test</h1>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',

  data: () => ({
    className: 'dashboard',
  }),
};
</script>
