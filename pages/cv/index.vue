<template>
  <div class="container cv__container">
    <div class="cv__wrapper">
      <section class="section section__summary">
        <div class="cv-photo">
          <img src="/images/avatar.jpg" alt="avatar" class="cv-photo__avatar">
        </div>
        <div class="summary">
          <div class="summary__title">Tejender Singh</div>
          <div class="summary__sub-title">Front End Developer</div>
          <div class="summary__links">
            <div class="link-item">
              <font-awesome-icon :icon="['fas', 'envelope']"/>
              <a href="mailto:singhtj22@gmail.com">singhtj22@gmail.com</a>
            </div>
            <div class="link-item">
              <font-awesome-icon :icon="['fab', 'linkedin']"/>
              <a href="https://www.linkedin.com/in/tejender-singh/" target="_blank">Tejender Singh</a>
            </div>
            <div class="link-item"></div>
          </div>
          <p>A Web Developer with experience building Responsive, Interactive and User Friendly Websites and Web Applications. I am fully knowledgeable in front-end development technologies HTML, CSS, SCSS and JavaScript. I also have experience working with css fremeworks like Bootstrap, Bulma and popular JavaScript libraries/frameworks, i.e. React, Vue.js and Nuxt.js</p>
          <br>
          <p>Proficient in development tools like Git version control, npm, Gulp and familiar with building REST APIs using Node.js, Express and MongoDB.</p>
        </div>
      </section>

      <section class="section section__education">
        <div class="section-title">Education</div>
        <div>
          <DetailSection
            title="Graduate Diploma in Retail Management"
            subtitle="Retail Business Management College, New Zealand"
            date="Oct 2015 - Oct 2016"
          ></DetailSection>
          <DetailSection
            title="Graduate Diploma in Information and Communication Technology"
            subtitle="Ara Institute of Canterbury, New Zealand"
            date="July 2013 - July 2014"
          ></DetailSection>
          <DetailSection
            title="Bachelor of Computer Application"
            subtitle="Maharaja Ganga Singh University, India"
            date="July 2008 - July 2011"
          ></DetailSection>
        </div>
      </section>

      <section class="section section__skills">
        <div class="section-title">Skills</div>
        <div>
          <div class="skills">
            <ul>
              <div class="skills__title">Technical</div>
              <li>HTML5/CSS3</li>
              <li>SASS</li>
              <li>JavaScript</li>
              <li>React.js</li>
              <li>vue.js</li>
              <li>Nuxt.js</li>
              <li>Node.js</li>
              <li>Express</li>
              <li>MongoDB</li>
            </ul>
            <ul>
              <div class="skills__title">Tools</div>
              <li>Git</li>
              <li>Npm</li>
              <li>Gulp</li>
            </ul>
            <ul>
              <div class="skills__title">Others</div>
              <li>Good Communication skills</li>
              <li>Eye for detail</li>
              <li>Fast learner</li>
              <li>Problem solving skills</li>
              <li>Highly adaptable</li>
            </ul>
          </div>
        </div>
      </section>

      <section class="section section__education">
        <div class="section-title">Experience</div>
        <div>
          <DetailSection
            title="Allied Security"
            subtitle="Security Officer"
            date="Oct 2016 - present"
          ></DetailSection>
          <DetailSection
            title="First Security"
            subtitle="Security Officer"
            date="Aug 2014 - June 2015"
          ></DetailSection>
        </div>
      </section>

      <section class="section section__interests">
        <div class="section-title">Interests</div>
        <div class="interests">
          <font-awesome-icon class="interests__icons" :icon="['fas', 'bicycle']"/>
          <font-awesome-icon class="interests__icons" :icon="['fas', 'code']"/>
          <font-awesome-icon class="interests__icons" :icon="['fas', 'music']"/>
        </div>
      </section>
      <section class="section section__references">
        <div class="section-title">Reference</div>
        <div class="references">
          <p class="references__text">Referees available upon request</p>
        </div>
      </section>
    </div>
  </div>
</template>


<script>
import DetailSection from "~/components/cv/DetailSection";
import PageHeader from "~/components/common/PageHeader";

export default {
  components: {
    DetailSection
  },
  head() {
    return {
      title: "My qualifications and skills"
    };
  }
};
</script>

<style scoped lang="scss">
//
.cv__container {
  background: #f2f2f2;
  color: var(--cv-font-color);
  line-height: 1.5;
  padding: 4rem 2rem;
  .cv__wrapper {
    background: #fff;
    max-width: 960px;
    padding: 32px;
    margin: 0 auto;
    box-shadow: 0 2px 4px rgba($color: #000000, $alpha: 0.1);
    .section {
      display: grid;
      grid-template-columns: 1fr;
      grid-gap: 1.5rem;
      padding: 1.5rem;
      border-bottom: 1px solid lightgrey;
      @include medium {
        grid-template-columns: 120px 4fr;
      }
      &:last-child {
        border-bottom: none;
      }
      .section-title {
        font-size: 1.5rem;
        font-family: "Mosk-extra-bold", Helvetica, sans-serif;
      }
    }
    .section__summary {
      .cv-photo {
        &__avatar {
          width: 120px;
          height: 120px;
          border-radius: 50%;
        }
      }
      .summary {
        &__title {
          font-size: 2rem;
          font-family: "Mosk-extra-bold", Helvetica, sans-serif;

          line-height: 1;
          @include medium {
            font-size: 2.3rem;
          }
        }
        &__sub-title {
          font-family: "Mosk-bold", Helvetica, sans-serif;
          font-size: 1.2rem;
          color: var(--main);
          @include medium {
            font-size: 1.4rem;
          }
        }
        &__links {
          display: flex;
          flex-direction: column;
          margin: 0.6rem 0 1.25rem 0;
          line-height: 1.3;
          @include large {
            flex-direction: row;
          }
          .link-item {
            display: flex;
            align-items: center;
            margin-right: 5px;
            flex: 1;
            a {
              margin-left: 5px;
              color: #0652dd;
              font-size: 0.9rem;
              line-height: 1.4;
            }
          }
        }
      }
    }
    .section__skills {
      .skills {
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1.25rem;
        @include medium {
          grid-template-columns: repeat(2, 1fr);
        }
        @include large {
          grid-template-columns: repeat(3, 1fr);
        }
        ul {
          .skills__title {
            font-size: 1.2rem;
            font-family: "Mosk-bold", Helvetica, sans-serif;
            margin-bottom: 0.5rem;
          }
          li {
            margin-left: 1.125rem;
            font-family: "Mosk-normal", Helvetica, sans-serif;
          }
        }
      }
    }
    .section__interests {
      .interests {
        display: flex;
        height: 100%;
        align-items: center;
        font-size: 2rem;
        opacity: 0.9;
        &__icons {
          margin-right: 2rem;
        }
      }
    }
    .section__references {
      .references {
        display: flex;
        align-items: center;
      }
    }
  }
}
</style>