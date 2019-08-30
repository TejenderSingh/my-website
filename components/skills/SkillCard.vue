<template>
  <div class="skill-card">
    <figure>
      <img :src="`/images/${imgSrc}.png`" alt="html" loading="lazy" class="skill-card__img" />
    </figure>
    <p class="skill-card__text">{{imgName}}</p>
  </div>
</template>

<script>
export default {
  props: {
    imgName: {
      type: String,
      required: true
    },
    imgSrc: {
      type: String
    }
  }
};
</script>

<style scoped lang="scss">
.skill-card {
  display: grid;
  grid-template-rows: 1fr 4rem;
  background: var(--card-title-bg);
  box-shadow: 0 3px 5px rgba(0, 0, 0, 0.1);
  position: relative;
  z-index: 10;
  @include medium {
    grid-template-columns: 0.6fr 1fr;
    grid-template-rows: auto;
  }
  @include large {
    grid-template-columns: none;
    grid-template-rows: 1fr 4rem;
  }
  &__img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    background: white;
  }
  &__text {
    font-size: 1.3rem;
    color: var(--card-font-color);
    text-align: center;
    align-self: center;
    font-family: var(--font-extra-bold);
  }
}
</style>