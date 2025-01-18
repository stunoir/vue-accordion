<script setup>
  import { ref } from 'vue'

  const props = defineProps({
    items: {
      type: Array,
      required: true
    }
  })

  // local reactive copy of the passed array
  const reactiveItems = ref([...props.items])

  const toggleAccordion = (idx) => {
    reactiveItems.value = reactiveItems.value.map((item, index) => ({
      ...item,
      open: index === idx ? !item.open : false
    }))
  }
</script>

<template>
  <div class="accordion">
    <div v-for="(item, index) in reactiveItems" :key="index" class="accordion-item">
      <button
        @click="toggleAccordion(index)"
        class="accordion-button"
        :class="{ 'is-active': item.open }"
        :aria-expanded="item.open"
      >
        {{ item.title }}<span aria-hidden="true" class="szicon-keyboard-arrow-down"></span>
      </button>
      <div class="accordion-panel" :class="{ 'is-open': item.open }">
        <div class="inner-panel wysiwyg">
          <p>{{ item.content }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
