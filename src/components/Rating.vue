<template>
  <div class="rating">
    <ul class="list">
      <li
        @click="rate(item)"
        v-for="item in maxItems"
        :key="item.index"
        class="vue"
        :class="{ active: item <= items }"
      >
        <icon name="brands/vuejs" scale="3" />
      </li>
    </ul>
    <div v-if="hasCounter">{{ items }} / {{ maxItems }}</div>
  </div>
</template>
<script>
import "vue-awesome/icons/brands/vuejs";
import Icon from "vue-awesome/components/Icon";

export default {
  name: "Rating",
  components: { Icon },
  props: ["grade", "maxItems", "hasCounter"],
  data() {
    return {
      items: this.grade
    };
  },
  methods: {
    rate(item) {
      if (typeof item === "number" && item <= this.maxItems && item >= 0) {
        this.items = this.items === item ? item - 1 : item;
      }
    }
  }
};
</script>
<style scoped>
.rating {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Roboto", sans-serif;
  font-size: 24px;
  color: #a7a8a8;
}
.list {
  margin: 00;
  padding: 0;
  list-style-type: none;
}
.list:hover .vue {
  color: #3aa273;
}
.vue {
  display: inline-block;
  cursor: pointer;
}
.vue:hover ~ .vue:not(.active) {
  color: inherit;
}
.active {
  color: #3aa273;
}
</style>
