<template>
  <div class="main-container">
    <div class="title__container">
      <div>
        <p class="title">{{title}}</p>
        <p class="sub-title">{{subtitle}}</p>
      </div>
      <p class="date">{{date}}</p>
    </div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      dafault: "title"
    },
    subtitle: {
      type: String,
      dafault: "subtitle"
    },
    date: {
      type: String,
      dafault: "jan 2014 - jan 2015"
    }
  }
};
</script>

<style scoped lang="scss">
.main-container {
  padding-bottom: 1.5rem;
  margin-bottom: 1.5rem;
  border-bottom: 1px solid lightgrey;
  &:last-child {
    border-bottom: none;
    margin-bottom: 0;
    padding-bottom: 0;
  }
  .title__container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    font-size: 1.2rem;
    @include large {
      flex-direction: row;
    }
    .title {
      font-size: 1.2rem;
      font-family: var(--font-bold);
    }
    .sub-title {
      font-size: 1rem;
    }
    .date {
      font-size: 0.9rem;
      margin-top: 0.4rem;
    }
  }
}
</style>