<template>
  <div class="container">
    <PageHeader name="My work"/>
    <div class="wrapper work__wrapper">
      <WorkCard
        v-for="card in cardDetails"
        :key="card.id"
        :cardTitle="card.title"
        :cardUrl="card.target"
        :cardImg="card.img"
        :tags="card.tags"
      />
    </div>
  </div>
</template>

<script>
import PageHeader from "~/components/common/PageHeader";
import WorkCard from "~/components/work/WorkCard";
export default {
  components: {
    PageHeader,
    WorkCard
  },
  head() {
    return {
      title: "My work"
    };
  },
  data() {
    return {
      cardDetails: [
        {
          title: "Node REST API",
          id: "7",
          target: "https://github.com/TejenderSingh/node-rest-api",
          img: "node",
          tags: ["Node.js", "Express", "MongoDB", "Joi"]
        },
        {
          title: "React-Dark Mode",
          id: "6",
          target: "https://github.com/TejenderSingh/react-dark-mode",
          img: "react",
          tags: ["React.js", "CSS"]
        },
        {
          title: "Nuxt.js and Storyblok blog",
          id: "5",
          target: "https://github.com/TejenderSingh/nuxt.js-and-storyblok-blog",
          img: "nuxt-storyblok",
          tags: ["Nuxt.js", "Storyblok", "Bulma"]
        },
        {
          title: "React todo app",
          id: "4",
          target: "https://github.com/TejenderSingh/react-todo-app",
          img: "react",
          tags: ["React.js", "Bulma"]
        },
        {
          title: "Vue todo app",
          id: "3",
          target: "https://github.com/TejenderSingh/vue.js-todo-app",
          img: "vue",
          tags: ["Vue.js", "Buefy"]
        },
        {
          title: "Who Dares Wins",
          id: "2",
          target: "https://github.com/TejenderSingh/who-dares-wins-vuejs",
          img: "who-dares-wins",
          tags: ["Vue.js", "Firebase", "Buefy"]
        },
        {
          title: "React Recipe app",
          id: "1",
          target: "https://github.com/TejenderSingh/Recipe-App-ReactJS",
          img: "react",
          tags: ["React.js", "Bootstrap"]
        }
      ]
    };
  }
};
</script>

<style scoped lang="scss">
.work__wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  grid-gap: 1.5rem;
  @include large {
    grid-template-columns: repeat(auto-fit, minmax(285px, 1fr));
    grid-gap: 2rem;
  }
}
</style>
