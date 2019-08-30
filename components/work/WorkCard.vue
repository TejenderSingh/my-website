<template>
  <a :href="cardUrl" target="_blank" class="work">
    <div class="work-card">
      <img :src="`/images/${cardImg}.png`" alt="project" loading="lazy" class="work-card__img" />
      <div class="work-card__text">
        <h2>{{cardTitle}}</h2>
        <div class="tags">
          <span v-for="tag in tags" :key="tag">{{tag}}</span>
        </div>
      </div>
    </div>
  </a>
</template>

<script>
export default {
  props: {
    cardTitle: {
      type: String
    },
    cardUrl: {
      type: String
    },
    cardImg: {
      type: String
    },
    tags: {
      type: Array
    }
  }
};
</script>

<style lang="scss">
.work {
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  border-radius: 0.3em;
  .work-card {
    position: relative;
    &__img {
      border-radius: 0.3em;
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    &__text {
      position: absolute;
      bottom: 0;
      min-width: 100%;
      border-bottom-left-radius: 0.3em;
      border-bottom-right-radius: 0.3em;
      background: var(--card-title-bg);
      padding: 1.2rem 1.2rem 0 1.2rem;
      h2 {
        font-size: 1.3rem;
        margin-bottom: 12px;
        color: var(--card-font-color);
        @include medium {
          font-size: 1.5rem;
        }
      }
      .tags {
        margin-bottom: 1.2rem;
        span {
          display: inline-block;
          font-size: 0.7rem;
          font-family: var(--font-thin);
          color: var(--main-light);
          background: var(--card-tag-bg);
          margin-right: 0.5rem;
          padding: 0.2rem 0.5rem;
          border-radius: 1.5rem;
          @include medium {
            font-size: 0.8rem;
          }
        }
      }
    }
  }
}
</style>