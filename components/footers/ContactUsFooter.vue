<template>
  <footer ref="contactUsFooter" id="contact-us-footer">
    <h1 class="heading">See The LearnRoom in Action</h1>
    <div class="highlight">
      Lorem Ipsum is simply dummy text of the printing lorem
    </div>

    <div class="content">
      <div class="first-element">
        <div class="accordion-container">
          <!-- Accordion 1 -->
          <div class="accordion" @click="accordionClicked()">
            <span>Preview A Live Online Class</span>
            <i class="fas fa-angle-down down"></i>
            <i class="fas fa-angle-up up"></i>
          </div>
          <div class="panel">
            <div class="panel-content">
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
            </div>
          </div>

          <!-- Accordion 2 -->
          <div class="accordion" @click="accordionClicked()">
            <span>Preview A Live Online Class</span>
            <i class="fas fa-angle-down down"></i>
            <i class="fas fa-angle-up up"></i>
          </div>
          <div class="panel">
            <div class="panel-content">
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
            </div>
          </div>

		  <!-- Accordion 3 -->
          <div class="accordion" @click="accordionClicked()">
            <span>Preview A Live Online Class</span>
            <i class="fas fa-angle-down down"></i>
            <i class="fas fa-angle-up up"></i>
          </div>
          <div class="panel">
            <div class="panel-content">
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                Necessitatibus, autem.
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="video-container">
        <div class="placeholder-image">
          <i class="far fa-play-circle"></i>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  methods: {
    accordionClicked() {
      const accordion = event.currentTarget;
      const panel = accordion.nextElementSibling;
      const contactUsFooter = this.$refs.contactUsFooter;

      const isActive = accordion.classList.contains("active");

      for (let acc of contactUsFooter.getElementsByClassName("accordion")) {
        if (acc.classList.contains("active")) {
          acc.nextElementSibling.style.maxHeight = "0px";
          acc.classList.remove("active");
        }
      }

      if (!isActive) {
        panel.style.maxHeight = `${panel.scrollHeight}px`;
        accordion.classList.add("active");
      } else {
        panel.style.maxHeight = `0px`;
        accordion.classList.remove("active");
      }
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

#contact-us-footer {
  padding: 28px var(--body-padding);
  background: $primaryColor;
  color: white;
  .heading {
    text-align: center;
    font-size: 1.3rem;
    font-weight: 500;
    margin-bottom: 4px;
  }
  .highlight {
    text-align: center;
    font-size: 0.9rem;
  }
  .content {
    display: grid;
    grid-template-columns:  1fr;
    gap: 32px;
    margin: 16px 0;
    margin-top: 48px;

	@media only screen and (min-width: 768px) {
		// gap: 16px;
		grid-template-columns: 1fr 1fr;
	}
  }

  .accordion-container {
	  
	  @media only screen and (min-width: 768px) {
		  margin-left: auto;
		width: 80%;
		max-width: 350px;
		gap: 16px;
		grid-template-columns: 1fr 1fr;
	}
    .accordion {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: black;
      padding: 0 16px;
      height: 30px;
      border-radius: 5px;
      cursor: pointer;

      .up {
        display: none;
      }
      .down {
        display: inline-block;
      }

      &.active {
        .up {
          display: inline-block;
        }
        .down {
          display: none;
        }
      }
    }

    .panel {
      background: $offWhite;
      color: $textColor;
      margin-bottom: 16px;
      font-size: 0.9rem;
      max-height: 0;
      transition: max-height ease 0.2s;
      overflow: hidden;

      .panel-content {
        padding: 12px;
      }
    }
  }

  .video-container {
    border-radius: 5px;
    overflow: hidden;
    .placeholder-image {
      height: 200px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3rem;
      background: #cdc9c9;
      color: #707070;
    }
  }
}
</style>