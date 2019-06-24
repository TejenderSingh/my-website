<template>
  <div class="container skills__container">
    <PageHeader name="Skills"/>
    <div class="wrapper skills__wrapper">
      <section class="skills">
        <SkillCard
          v-for="skill in skills"
          :key="skill.title"
          :imgName="skill.title"
          :imgSrc="skill.imgSource"
        />
      </section>
    </div>
  </div>
</template>

<script>
import PageHeader from "~/components/common/PageHeader";
import SkillCard from "~/components/skills/SkillCard";
export default {
  components: {
    PageHeader,
    SkillCard
  },
  head() {
    return {
      title: "Languages I speak and tools I use"
    };
  },
  data() {
    return {
      skills: [
        {
          title: "HTML5",
          imgSource: "html5"
        },
        {
          title: "CSS3",
          imgSource: "css3"
        },
        {
          title: "Sass",
          imgSource: "sass"
        },
        {
          title: "JavaScript",
          imgSource: "js"
        },
        {
          title: "ES6",
          imgSource: "es6"
        },
        {
          title: "Vue.js",
          imgSource: "vue"
        },
        {
          title: "Nuxt.js",
          imgSource: "nuxt"
        },
        {
          title: "React.js",
          imgSource: "react"
        },
        {
          title: "Node.js",
          imgSource: "node"
        },
        {
          title: "Express",
          imgSource: "express"
        },
        {
          title: "MongoDB",
          imgSource: "mongodb"
        },
        {
          title: "Bootstrap",
          imgSource: "bootstrap"
        },
        {
          title: "Bulma",
          imgSource: "bulma"
        },
        {
          title: "Materialize",
          imgSource: "materialize"
        },
        {
          title: "Git",
          imgSource: "git"
        },
        {
          title: "Github",
          imgSource: "github"
        },
        {
          title: "Gulp",
          imgSource: "gulp"
        },
        {
          title: "VS Code",
          imgSource: "vscode"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.skills__container {
  .skills__wrapper {
    .skills {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 1em;
      @include small {
        grid-template-columns: repeat(3, 1fr);
      }
      @include medium {
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
        grid-gap: 1em;
      }
    }
  }
}
</style>
