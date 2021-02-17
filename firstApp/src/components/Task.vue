<template>
  <li>
    <div><slot></slot>{{ index + 1 }}</div>
    <small>{{ task.date }} : {{ task.time }}</small>
  </li>
</template>

<script>
export default {
  props: ['task', 'index']
}
</script>

<style></style>
