<template>
  <div :class="['vx-tab--item', {'vx-flexbox--item': $parent.layout=='default','is-active': $parent.active === name}]" @click="handleClick(name)">
    <span v-if="$parent.underlineWidth" class="vx-tab--item-text">
      <slot></slot>
    </span>
    <slot v-else></slot>
  </div>
</template>

<script>
export default {
  componentName: 'TabItem',
  props: {
    name: {
      type: [Number, String, Object],
      required: true
    }
  },
  methods: {
    handleClick (name) {
      this.$parent.change(name)
    }
  }
}
</script>
