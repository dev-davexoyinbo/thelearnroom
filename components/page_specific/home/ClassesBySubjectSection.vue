<template>
  <section id="classes-by-subject-section">
    <h1 class="heading">Classes by Subject</h1>
    <div class="cards-container">
      <div class="single-card-container" v-for="(datum, i) in clasesBySubjectData" :key="i">
        <class-by-subject-card :data="datum" />
      </div>
    </div>
  </section>
</template>

<script>
import ClassBySubjectCard from "./ClassBySubjectCard.vue";
export default {
  components: { ClassBySubjectCard },
  data() {
    return {
      clasesBySubjectData: [
        {
          iconClass: {
            far: true,
            "fa-object-group": true,
          },
          heading: "Arts",
          classes: [
            {
              title: "Drawing",
              link: "#",
            },
            {
              title: "Photography",
              link: "#",
            },
            {
              title: "Dance",
              link: "#",
            },
            {
              title: "Theater",
              link: "#",
            },
            {
              title: "Film",
              link: "#",
            },
            {
              title: "Sewing",
              link: "#",
            },
            {
              title: "All art classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fas: true,
            "fa-laptop-code": true,
          },
          heading: "Coding and Tech",
          classes: [
            {
              title: "coding",
              link: "#",
            },
            {
              title: "Video game design",
              link: "#",
            },
            {
              title: "Robotics",
              link: "#",
            },
            {
              title: "Engineering",
              link: "#",
            },
            {
              title: "Internet Safety",
              link: "#",
            },
            {
              title: "Animation",
              link: "#",
            },
            {
              title: "All Coding & Tech classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fab: true,
            "fa-keybase": true,
          },
          heading: "English",
          classes: [
            {
              title: "creative writing",
              link: "#",
            },
            {
              title: "Grammar",
              link: "#",
            },
            {
              title: "Spelling",
              link: "#",
            },
            {
              title: "Book club",
              link: "#",
            },
            {
              title: "Essay writing",
              link: "#",
            },
            {
              title: "Poetry",
              link: "#",
            },
			{
              title: "Literature",
              link: "#",
            },
            {
              title: "All English classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fas: true,
            "fa-music": true,
          },
          heading: "Music",
          classes: [
            {
              title: "Guitar",
              link: "#",
            },
            {
              title: "Piano",
              link: "#",
            },
            {
              title: "Singing",
              link: "#",
            },
            {
              title: "Composers",
              link: "#",
            },
            {
              title: "Music Theory",
              link: "#",
            },
            {
              title: "All Music Classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fas: true,
            "fa-camera-retro": true,
          },
          heading: "Film & Photography",
          classes: [
            {
              title: "Nature photography",
              link: "#",
            },
            {
              title: "Drama",
              link: "#",
            },
            {
              title: "cinematography",
              link: "#",
            },
            {
              title: "Editing",
              link: "#",
            },
            {
              title: "Videography",
              link: "#",
            },
			{
              title: "imagearea",
              link: "#",
            },
            {
              title: "All Film & Photography Classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fas: true,
            "fa-language": true,
          },
          heading: "Language",
          classes: [
            {
              title: "Spanish",
              link: "#",
            },
            {
              title: "American Sign Language",
              link: "#",
            },
            {
              title: "French",
              link: "#",
            },
            {
              title: "Japanese",
              link: "#",
            },
            {
              title: "Latin",
              link: "#",
            },
			{
              title: "German",
              link: "#",
            },
			{
              title: "Greek",
              link: "#",
            },
			{
              title: "Italian",
              link: "#",
            },
            {
              title: "All Languages Classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            far: true,
            "fa-handshake": true,
          },
          heading: "Life Skills",
          classes: [
            {
              title: "Cooking",
              link: "#",
            },
            {
              title: "Financial Skills",
              link: "#",
            },
            {
              title: "Study Skills",
              link: "#",
            },
            {
              title: "Social Skills",
              link: "#",
            },
            {
              title: "Critical Thinking",
              link: "#",
            },
            {
              title: "All Life Skills Classes",
              link: "#",
            },
          ],
        },
		{
          iconClass: {
            fas: true,
            "fa-globe-europe": true,
          },
          heading: "Social Studies",
          classes: [
            {
              title: "Geography",
              link: "#",
            },
            {
              title: "World history",
              link: "#",
            },
            {
              title: "Anthropology",
              link: "#",
            },
            {
              title: "Economics",
              link: "#",
            },
            {
              title: "Politics",
              link: "#",
            },
            {
              title: "All Social Studies Classes",
              link: "#",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#classes-by-subject-section {
  margin-top: 16px 0;
  padding: 32px var(--body-padding);
  background: $offWhite;

  & > .heading {color: black;
    font-weight: 400;
    font-size: 1.7rem;
    margin-bottom: 8px;
    text-align: center;
    margin-bottom: 32px;
    
  }

  .cards-container {
	  display: grid;
	  grid-template-columns: 1fr;
	  gap: 16px;

	  @media only screen and (min-width: 768px) {
		  grid-template-columns: 1fr 1fr;

	  }
  }
}
</style>