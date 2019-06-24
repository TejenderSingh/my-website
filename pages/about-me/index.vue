<template>
  <div class="container container__about">
    <div class="wrapper wrapper__about">
      <img class="about__photo" src="/images/my-img.jpg" alt="my image">
      <div class="about">
        <h1 class="about__title">About me</h1>
        <p class="about__subtitle">Tejender Singh - Web Developer</p>
        <div class="about__content">
          <p>I love building responsive, interactive and user friendly Websites and Web Applications using HTML, CSS and JavaScript. I have experience working with some of the latest technologies including React.js, Vue.js and Nuxt.js. I am passionate about Web Development and Programming where I can make a difference and feel proud of being able to create something that is distinctive and positively impact people's lives.</p>
          <br>
          <p>I also like meeting new people and talking about technology so I have joined a couple of meet up groups in Christchurch. These groups provide me an obvious place to meet other programmers and IT professionals, learn more about my language of choice and get advice to accomplish my goals.</p>
          <br>
          <p>Apart from programming, I enjoy cycling and spending time with family/friends.</p>
        </div>
        <div class="about__social-icons">
          <a href="https://www.linkedin.com/in/tejender-singh" target="_blank">
            <font-awesome-icon :icon="['fab', 'linkedin']"/>
          </a>
          <a href="https://github.com/TejenderSingh" target="_blank">
            <font-awesome-icon :icon="['fab', 'github']"/>
          </a>
          <a href="mailto:singhtj22@gmail.com">
            <font-awesome-icon :icon="['fas', 'envelope']"/>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About me"
    };
  }
};
</script>

<style scoped lang="scss">
.container__about {
  .wrapper__about {
    padding: 6rem 2rem 2rem 2rem;
    display: flex;
    flex-direction: column;
    @include large {
      flex-direction: row-reverse;
    }
    .about__photo {
      width: 100%;
      max-width: 300px;
      height: 400px;
      object-fit: cover;
      @include medium {
        max-width: 350px;
        height: 450px;
      }
    }
    .about {
      padding: 2rem 0 0 0;
      color: var(--about-font-color);
      @include large {
        margin-right: 3rem;
        padding: 2rem 0;
      }
      @include desktop {
        margin-right: 5rem;
      }
      &__title {
        text-transform: uppercase;
        margin-left: 0;
        font-size: 2.5rem;
        color: var(--main-darker);
        @include medium {
          font-size: 3rem;
        }
      }
      &__subtitle {
        margin: 0.5rem 0 2rem 0;
        font-size: 1.2rem;
        font-family: var(--font-thin);
      }
      &__content p {
        font-size: 1rem;
        line-height: 1.7;
      }
      &__social-icons {
        margin: 4rem 0 0 0;
        a {
          font-size: 2rem;
          margin-right: 2rem;
          color: var(--about-social-color);
        }
      }
    }
  }
}
</style>
