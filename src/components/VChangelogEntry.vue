<template functional>
  <li class="changelog-item-entry">
    {{ props.entry.title }}
    <a
      href="#"
      v-if="props.entry.reference"
      class="changelog-item-entry-ref"
    >#{{ props.entry.reference }}</a>
    <a href="#" v-if="props.entry.author">@{{ props.entry.author }}</a>

    <ul v-if="$slots.entries" class="changelog-item-entries">
      <slot name="entries"/>
    </ul>
  </li>
</template>

<script>
export default {
  name: "VChangelogEntry",

  props: {
    entry: {
      type: Object,
      required: true
    }
  }
};
</script>
