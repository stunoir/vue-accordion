# Accordion Component

This Vue component implements a responsive and accessible accordion, allowing users to toggle content panels open or closed. It is built using the Composition API and supports dynamic data passed as props.

---

## Features

- **Dynamic Data**: Accepts an array of items via props, each containing a title, content, and `open` state.
- **Accessibility**: Utilises proper ARIA attributes (`aria-expanded`) for better accessibility.
- **Reactivity**: Maintains a local reactive state for interactive toggling.
- **Scoped Styles**: Easily customisable with scoped styles.

---

## Props

### `items` (required)

- **Type**: `Array`
- **Description**: An array of objects that define the accordion's structure. Each object should have the following fields:
  - `title` (string): The title of the accordion section.
  - `content` (string): The content displayed when the section is expanded.
  - `open` (boolean): Indicates whether the section is initially open.

### Example

```javascript
;[
  {
    title: 'Section 1',
    content: 'This is the content for section 1.',
    open: false
  },
  {
    title: 'Section 2',
    content: 'This is the content for section 2.',
    open: false
  }
]
```

---

## Usage

### Basic Setup

```vue
<template>
  <Accordion :items="accordionItems" />
</template>

<script setup>
  import Accordion from './Accordion.vue'

  const accordionItems = [
    {
      title: 'Section 1',
      content: 'Content for section 1.',
      open: false
    },
    {
      title: 'Section 2',
      content: 'Content for section 2.',
      open: false
    },
    {
      title: 'Section 3',
      content: 'Content for section 3.',
      open: false
    }
  ]
</script>
```

---

## Component Details

### Reactive State

The component makes a local reactive copy of the `items` array using `ref` to manage the `open` state of each section.

```javascript
const reactiveItems = ref([...props.items])
```

### Toggling Logic

The `toggleAccordion` function updates the `open` state for the selected index, while ensuring only one section is open at a time.

```javascript
const toggleAccordion = (idx) => {
  reactiveItems.value = reactiveItems.value.map((item, index) => ({
    ...item,
    open: index === idx ? !item.open : false
  }))
}
```

---

## Accessibility Features

- **Keyboard Navigation**: Fully navigable using a keyboard.
- **ARIA Attributes**:
  - `aria-expanded` indicates the open/closed state of each accordion button.
  - Proper semantic structure with `<button>` and `<div>` for headings and panels.

---

## Styling

The component includes scoped styles for easy customisation. Add or modify styles to fit your design system.

```css
<style scoped>
.accordion {
  /* Add accordion container styles */
}

.accordion-button {
  /* Style for accordion buttons */
}

.accordion-panel {
  /* Style for content panels */
}
</style>
```

---

## Customisation

Feel free to extend or modify the component:

- Add animations to the panel transitions.
- Introduce support for multiple open panels if needed.
- Use custom icons or button designs.
