
![Logo](https://images.squarespace-cdn.com/content/v1/5f29938650d18d61c97cc759/8fbe887d-3e80-454d-adbe-fb2d5e4b3df9/SmartWorkPlusLogo%28White%29%28NoSubtitle%29.png?format=110w)


# Nuxt Coding Structure

## Objective
The purpose of this document is to establish a coherent and universally understood coding structure for Vue 3/Nuxt projects within our company. Adhering to these guidelines will ensure codebase maintainability, readability, and uniformity.

## `.vue` File Structure
Each `.vue` file must be organized in the following manner:

1. **`<template></template>`**: Where any HTML markup goes.
2. **`<script setup></script>`**: Using setup as we prefer composition api.
3. **`<style></style>`**: Though rarely used (due to our usage of Tailwind CSS), this is where you'd place any component-specific styles.

### Example
```vue
<template>
  <!-- HTML Markup -->
</template>

<script setup>
  // JavaScript logic
</script>

<style>
  /* Component-specific styles */
</style>
```

## `<script setup>` Tag Structure
Within the `<script setup>` tag, organize your code in the following order:

### 1. Defining Page Meta
Implement page meta here.
```javascript
definePageMeta({
  layout: "control",
});
```

### 2. Constant Imports
Import third-party or internal constants at the top.
```javascript
const dayjs = useDayjs();
```

### 3. Pinia Stores
Initialize any Pina stores you intend to use.
```javascript
const heatStore = heatReportStore();
```

### 4. Props & Emits
Declare any props or emits here if needed.
```javascript
defineProps({
  title: String,
  temp: Number
})

defineEmits(['inFocus', 'submit'])
```

### 5. Static Constants, Variables, and 'Let' Declarations
Declare any static `const`, `var`, or `let` variables.
```javascript
const staticValue = 42;
let mutableValue = "changeable";
```

### 6. Reactive Constants (Primitive Types)
Declare reactive constants that hold primitive types like numbers and strings.
```javascript
const number = ref(1);
const text = ref("sample");
```

### 7. Reactive Constants (Objects and Arrays)
Declare reactive constants that hold objects or arrays.
```javascript
const obj = reactive({ key: "value" });
const arr = ref([]);
```

### 8. Computed or Watcher Values
Declare any computed values.
```javascript
const chartStore = computed(() => {});
watch(value,(newVal,oldVal) +> {});
```

### 9. Functions
Define any functions.
```javascript
const fetchReport = () => {
  // logic here
};
```

### 10. Lifecycle Hooks
Finally, implement any Vue lifecycle hooks like `onMounted`.
```javascript
onMounted(() => {
  // logic here
});
```

## Summary
By following these guidelines, we can streamline development whilst maintaining a easier-to-userstand code. Allows the team to quickly review code.
