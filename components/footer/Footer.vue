<template>
  <div class="footer">
    <div class="footer__content">
      <p class="email">
        <font-awesome-icon class="icon__envelope" :icon="['fas', 'envelope']"/>
        <span>singhtj22@gmail.com</span>
      </p>

      <div class="details">
        <span>Made with</span>
        <font-awesome-icon class="icon__heart" :icon="['fas', 'heart']"/>
        <span>and</span>
        <img class="nuxt__photo" src="/images/nuxt.png" alt="my image">
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.footer {
  width: 100%;
  padding: 1rem 0;
  background: var(--main-darker);
  @include medium {
    padding: 0.55rem 2rem;
  }
  &__content {
    max-width: calc(1280px - 4rem);
    font-size: 0.9rem;
    height: 40px;
    margin: 0 auto;
    color: var(--main-light);
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    @include medium {
      flex-direction: row;
      justify-content: space-between;
    }
    .email {
      margin-bottom: 0.4rem;
      @include medium {
        margin-bottom: 0;
      }
    }
    .details {
      display: flex;
      justify-content: center;
      align-items: center;
      img {
        width: 20px;
        margin: 0 0 0 0.3rem;
      }
    }
    .icon__heart {
      color: #c23616;
      margin: 0 0.3rem;
    }
    .icon__envelope {
      color: var(--main-accent);
    }
  }
}
</style>