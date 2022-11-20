<template>
  <li>
    <img
      src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png"
      alt=""
      width="200"
      height="200"
    />
    <slot name="card-header"></slot>
    <slot name="card-button"></slot>
    <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {};
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: purple;
  padding: 0.5rem;
  color: white;
}
</style>
