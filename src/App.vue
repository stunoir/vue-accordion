<script setup>
  import AccordionComponent from './components/AccordionComponent.vue'
  import { ref } from 'vue'

  // demo content
  const items = ref([
    {
      title: 'Lorem Ipsum Dolor',
      content:
        'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin at magna vel augue viverra suscipit. Aenean a risus id lectus fermentum gravida vel non risus.',
      open: false
    },
    {
      title: 'Sed Vehicula Enim',
      content:
        'Sed vehicula enim et justo facilisis, nec tempor elit eleifend. Ut aliquet, ligula vel cursus laoreet, lorem magna posuere justo, id lacinia sapien nulla a lectus.',
      open: false
    },
    {
      title: 'Praesent Euismod',
      content:
        'Praesent euismod odio nec arcu hendrerit, a sodales est tristique. Cras sit amet nisi ac arcu dignissim pretium. Vestibulum consequat, urna in malesuada tincidunt, orci orci viverra purus, at mollis eros lorem vel nisl.',
      open: false
    },
    {
      title: 'Aenean Ultricies Nunc',
      content:
        'Aenean ultricies nunc vel massa pharetra, non vestibulum odio tincidunt. Suspendisse potenti. Integer vitae ante at metus posuere convallis in a purus.',
      open: false
    },
    {
      title: 'Curabitur Vitae',
      content:
        'Curabitur vitae velit at erat aliquam congue. Morbi vitae tortor cursus, pharetra sapien sed, cursus ex. Donec in nisi vel velit vulputate volutpat.',
      open: false
    }
  ])
</script>

<template>
  <div class="page-padder">
    <div class="grid-container">
      <div class="grid-x grid-padding-x align-center">
        <div class="cell medium-8">
          <h1>Accordion</h1>
          <p>
            This Vue component implements a responsive and accessible accordion, allowing users to toggle content panels
            open or closed. It is built using the Composition API and supports dynamic data passed as props.
          </p>
          <AccordionComponent :items="items"></AccordionComponent>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .page-padder {
    padding: 3rem 0;
  }
</style>
