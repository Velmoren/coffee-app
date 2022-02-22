<template>
    <div
    :class="classItem"
    @click="onEmmit"
  >
    <img :src="require(`@/assets/img/${card.image}`)" :alt="card.image" />
    <div class="best__item-title">{{ card.name }}</div>
    <div class="best__item-price">{{ card.price }}$</div>
  </div>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required: true,
    },
    classItem: {
      type: String,
      required: false,
    },
  },
  methods: {
    onEmmit() {
      this.$emit('navigate', this.card.id);
    }
  }
};
</script>