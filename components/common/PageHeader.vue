<template>
  <div>
    <h1 class="title">{{name}}</h1>
  </div>
</template>

<script>
export default {
  name: "PageHeader",
  props: {
    name: {
      type: String,
      default: "Title"
    }
  }
};
</script>

<style scoped lang="scss">
.title {
  padding: 2rem 0 0 0;
  text-align: center;
  color: var(--main-darker);
  font-size: 2.5rem;
  text-transform: uppercase;
  @include medium {
    font-size: 3rem;
  }
}
</style>
