<template>
  <div>
    <div class="card faq-card">
      <div class="card-content content">
        <h1 class="title">Frequently Asked Questions</h1>
        <p class="content">
          For general questions regarding the TechLabs Digital Shaper program,
          take a look at this Pages:
        </p>
        <a
          href="https://www.notion.so/techlabs/FAQ-for-Techies-41bb02ff48a940b0a97885e91c21671b"
          target="_new"
          class="techlabs-button faq-button"
        >
          <span class="icon">
            <Fas i="link" />
          </span>
          <span>FAQ for Techies</span>
        </a>
        <a
          href="https://www.notion.so/techlabs/Digital-Shaper-Programm-TechLabs-M-nster-cc36b85b067c4fa5942c3cb552450ddf"
          target="_new"
          class="techlabs-button faq-button"
        >
          <span class="icon">
            <Fas i="link" />
          </span>
          <span>Digital Shaper Programm @ TechLabs Münster</span>
        </a>
        <a
          href="https://www.notion.so/techlabs/Slack-Onboarding-Guide-e37c5e788da14f09a0b6a1bf7b9c0c02"
          target="_new"
          class="techlabs-button faq-button"
        >
          <span class="icon">
            <Fas i="link" />
          </span>
          <span>Slack Onboarding Guide</span>
        </a>
        <a
          href="https://www.notion.so/techlabs/Program-Onboarding-Guide-d0cfaf7bfa7a41d8ade8abb36c854ca2"
          target="_new"
          class="techlabs-button faq-button"
        >
          <span class="icon">
            <Fas i="link" />
          </span>
          <span>Program Onboarding Guide</span>
        </a>
      </div>
    </div>
    <div v-for="section in faq" :key="section.title" class="card faq-card">
      <div class="card-content content">
        <h2>{{ section.title }}</h2>
        <div
          v-for="(question, index) in section.questions"
          :key="question.title"
        >
          <Question :title="question.title" :content="question.content" />
          <div v-if="index < section.questions.length - 1" class="spacer" />
        </div>
      </div>
    </div>
  </div>
</template>

//
<script>
import Fas from '~/components/Fas'
// //import Question from '~/components/faq/Question'
// //import { faq } from '~/assets/content'

export default {
  components: {
    Fas
    // Question
  }
  // data() {
  //   return { faq }
  // }
}
</script>

<style lang="sass">
@import "~bulma/sass/utilities/_all"
@import "~/assets/variables"
@import "~bulma/sass/base/helpers"
@import "~bulma/sass/elements/content"

.faq-card
  margin-top: 2rem
  margin-bottom: 2rem
  margin-left: auto
  margin-right: auto
  max-width: $desktop * (9/12)
  border-radius: 8px

.faq-button
  vertical-align: ce
  margin: 0.5rem

.faq-card .content h2
  margin-bottom: 2rem
  &:after
    background: none repeat scroll 0 0 $primary
    bottom: -10px
    content: ""
    display: block
    height: 4px
    position: relative
    width: 3.5rem

.faq-card .content h3
  @extend .is-size-5
  margin-bottom: 1rem

.spacer
  height: 2px
  width: 100%
  background-color: $white-ter
  margin-top: 1rem
  margin-bottom: 1rem
</style>
