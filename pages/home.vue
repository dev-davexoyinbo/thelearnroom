<template>
  <div id="logged-in-home-page">
    <div class="topics-container">
      <div class="heading">Topic:</div>
      <div class="topics-buttons-container">
        <div
          class="single-button-container"
          v-for="topic in topics"
          :key="topic"
        >
          <generic-button :noBorder="true" :gray="true">
            {{ topic }}
          </generic-button>
        </div>
      </div>
    </div>
    <logged-in-online-classes-section>
      <template v-slot:header>Weekly Clubs and Social time</template>
    </logged-in-online-classes-section>

    <logged-in-online-classes-section>
      <template v-slot:header>Celebrate Black History Month</template>
    </logged-in-online-classes-section>

    <div class="weekly-clubs-button-container">
      <button class="weekly-clubs-button">Browse Weekly Clubs</button>
    </div>

    <logged-in-online-classes-section>
      <template v-slot:header>Starting within 24 hours</template>
    </logged-in-online-classes-section>

    <logged-in-online-classes-section>
      <template v-slot:header>Classes under $20</template>
    </logged-in-online-classes-section>

    <logged-in-online-classes-section>
      <template v-slot:header>Popular classes</template>
    </logged-in-online-classes-section>

    <browse-class-section />

    <classes-by-subject-section />

    <div class="home-page-section">
      <interested-in-something-section />
    </div>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
import InterestedInSomethingSection from "~/components/InterestedInSomethingSection.vue";
import BrowseClassSection from "~/components/page_specific/home/BrowseClassSection.vue";
import ClassesBySubjectSection from "~/components/page_specific/home/ClassesBySubjectSection.vue";
import CustomizeChildLearningSection from "~/components/page_specific/home/CustomizeChildLearningSection.vue";
import HeroSection from "~/components/page_specific/home/HeroSection.vue";
import LoggedInOnlineClassesSection from "~/components/page_specific/home/LoggedInOnlineClassesSection.vue";
import MeetOurTeacherSection from "~/components/page_specific/home/MeetOurTeacherSection.vue";
import TestimonialSection from "~/components/page_specific/home/TestimonialSection.vue";
export default {
  components: {
    HeroSection,
    CustomizeChildLearningSection,
    ClassesBySubjectSection,
    TestimonialSection,
    MeetOurTeacherSection,
    LoggedInOnlineClassesSection,
    BrowseClassSection,
    GenericButton,
    InterestedInSomethingSection,
  },
  data() {
    return {
      topics: [
        "Clubs",
        "Dancing",
        "Writing",
        "History",
        "Singing",
        "Gaming",
        "Anime",
        "Escape",
      ],
    };
  },
};
</script>

<style scoped lang="scss">
@import "~assets/styles/variables";

.home-page-section {
  padding: 32px var(--body-padding);
}

#logged-in-home-page {
  .topics-container {
    padding: 0 var(--body-padding);
    padding-right: 0;

    display: grid;
    grid-template-columns: max-content 1fr;
    gap: 16px;
    margin-top: 16px;
    align-items: center;
    .heading {
      color: black;
    }

    .topics-buttons-container {
      overflow-x: auto;
      display: flex;
      flex-wrap: nowrap;
      align-items: center;

      scrollbar-width: none;
      scroll-behavior: smooth;
      /* Firefox */
      -ms-overflow-style: none;
      /* IE 10+ */
      &::-webkit-scrollbar {
        width: 0px;
        height: 0px;
        background: transparent;
        /* Chrome/Safari/Webkit */
      }

      &::after {
        content: "";
        display: flex;
        width: 1px;
        min-width: 1px;
        max-width: 1px;
        height: 1px;
        margin-left: var(--body-padding);
      }

      @media only screen and (min-width: 768px) {
        margin-right: 0;
      }
      .single-button-container {
        margin-right: 10px;
        &:last-child {
          margin-right: 0;
        }
      }
    }
  }
  .weekly-clubs-button-container {
    display: flex;
    align-items: center;
    justify-content: center;
    .weekly-clubs-button {
      border-radius: 5px;
      height: 30px;
      padding-left: 12px;
      padding-right: 12px;
      outline: none;
      border: 1px solid $borderGray;
      background: white;
      box-shadow: 2px 2px 5px rgba($borderGray, 0.3);
      cursor: pointer;
    }
  }

  .interested-section {
    .interested-box {
      text-align: center;
      padding: 48px 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      background: $offWhite;
      border: 1px solid #bab9b9;
      border-radius: 5px;

      .heading {
        display: inline-block;
        font-size: 1.7rem;
        color: black;
        margin-bottom: 16px;
        font-weight: 400;
      }

      .submit-topic-button {
        color: white;
        border: none;
        outline: none;
        background: $primaryColor;
        padding-left: 16px;
        padding-right: 16px;
        height: 30px;
        border-radius: 5px;
        cursor: pointer;
        &:active {
          outline: none;
        }
      }
    }
  }
}
</style>

    