<template>
  <div :class="className">
    <h1 :class="`${className}__title`">{{ title }}</h1>
    <p
      v-html="description"
      :class="`${className}__description`" />

    <div class="pictures__container">
      <div
        v-for="(item, itemKey) in content.items"
        :key="itemKey"
        class="pic">
        <Picture
          aspect-ratio="200:300"
          :image="item.image" />
      </div>
    </div>

  </div>
</template>

<script>
import Picture from '@jdplc/jd-components/sfc/Picture.vue';

export default {
  name: 'Dashboard',

  components: {
    Picture,
  },

  data: () => ({
    className: 'dashboard',

    title: '[JD Component] Picture Test',

    description: 'Set the outer container <span style="color: blue">(blue)</span> to <strong>display: flex</strong>.<br>If there is a div around each picture <span style="color: red">(red)</span>, then set a flex value on this container, i.e. <strong>flex: 1</strong>, <strong>flex: 0 0 25%</strong> etc.',

    content: {
      items: [
        {
          image: 'https://picsum.photos/id/202/200/300',
        },
        {
          image: 'https://picsum.photos/id/305/200/300',
        },
      ],
    },
  }),
};
</script>

<style lang="scss">
.dashboard {
  .pictures__container {
    display: flex;
    border: 2px solid blue;

    .pic {
      border: 2px solid red;
      flex: 0 0 25%;
      margin: .5rem;
    }
  }
}
</style>
