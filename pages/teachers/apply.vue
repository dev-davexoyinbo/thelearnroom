<template>
  <div id="teachers-apply-page">
    <div class="about-the-learn-room apply-page-section">
      <h1 class="h1 heading">Step 1 : About The LearnRoom</h1>
      <div class="highlight">
        Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
        eiusmod tempor incididunt ut let dolore magn aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi
        <a href="#">learn more</a>
      </div>
      <generic-button :noBorder="true" :primary="true"
        >Take the LearnRoom</generic-button
      >
    </div>
    <form action="" class="form">
      <div class="apply-page-section">
        <h1 class="h1 heading">Step 2 : Take Your Application</h1>
        <div class="highlight">
          Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
          eiusmod tempor incididunt ut let dolore magn aliqua. Ut enim ad minim
          veniam, quis nostrud exercitation ullamco laboris nisi
          <a href="#">learn more</a>
        </div>

        <div class="form-group">
          <label for="">Public Teacher Name</label>
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
            eiusmod tempor
          </div>
          <input type="text" class="form-control sm" />
        </div>

        <div class="form-group">
          <label for="">Legal Name</label>
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
            eiusmod tempor
          </div>
          <input type="text" class="form-control sm" />
        </div>

        <div class="form-group">
          <label for="">Email</label>
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
            eiusmod tempor
          </div>
          <a href="#">Resend</a>
        </div>

        <div class="form-group">
          <label for="">Phone</label>
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
            eiusmod tempor
          </div>
          <input type="text" class="form-control sm" />
        </div>

        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let empor incididunt ut letdolore magn aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
          <textarea type="text" class="form-control"> </textarea>
        </div>

        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let empor incididunt ut letdolore magn aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
          <textarea type="text" class="form-control"> </textarea>
        </div>

        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let empor incididunt ut letdolore magn aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
          <textarea type="text" class="form-control"> </textarea>
        </div>
      </div>

      <div class="apply-page-section">
        <h1 class="h1 heading">Step 3 : Tell us about your classes</h1>
        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore magn empor incididunt ut letaliqua. Ut enim
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore empor incididunt ut let magn aliqua. Ut
            enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
          <textarea type="text" class="form-control"> </textarea>
        </div>
        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore magn empor incididunt ut letaliqua. Ut enim
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore empor incididunt ut let magn aliqua. Ut
            enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
          <textarea type="text" class="form-control"> </textarea>
        </div>
      </div>

      <div class="apply-page-section">
        <h1 class="h1 heading">Step 4 : Teach us something!</h1>
        <div class="form-group">
          <div class="highlight">
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore magn empor incididunt ut letaliqua. Ut enim
            Lorem ipsum dolor sit amet, consectetur adi pisicing eiusmod tempor
            incididunt ut let dolore empor incididunt ut let magn aliqua. Ut
            enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi
            <a href="#">learn more</a>
          </div>
        </div>
        <ul class="u-list">
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
        </ul>
      </div>

      <div class="record-button-section">
        <div class="record-button-container">
          <generic-button :noBorder="true" :primary="true"
            >Record Your Video</generic-button
          >
        </div>
        <ul class="u-list">
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
          <li>Lorem ipsum dolor sit amet, consectetur adi pisicing</li>
        </ul>
      </div>

      <div class="submit-section">
        <div class="form-group">
          <div class="tnc-container">
            <input hidden ref="tncCheckbox" class="tnc-checkbox" type="checkbox" name="" id="" />
            <div class="checkbox-placeholder" @click="tncCheckboxClicked()">
              <i class="fas fa-check"></i>
            </div>
            <span>

            I agree to the <a href="#"> Terms & Conditions , Community Standards</a> 
            </span>
          </div>
        </div>
        <button class="submit-button">Submit Application</button>
      </div>
    </form>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
export default {
  components: { GenericButton },
  layout: "teachers",
  methods: {
    tncCheckboxClicked(){ 
     const tncCheckbox = this.$refs.tncCheckbox
     tncCheckbox.checked = !tncCheckbox.checked 
    }
  }
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#teachers-apply-page {
  padding: 24px var(--body-padding);
  a {
    color: $primaryColor;
    text-decoration: none;
  }
  .apply-page-section {
    margin-bottom: 32px;
  }
  .heading {
    margin-bottom: 8px;
  }
  .highlight {
    font-size: 0.9rem;
    max-width: 600px;
  }

  .heading + .highlight {
    margin-bottom: 12px;
  }

  .form {
    font-size: 0.9rem;
    input.form-control {
      height: 30px;
    }
  }

  .record-button-section {
    .u-list {
      margin-top: 8px;
    }
    @media only screen and (min-width: 768px) {
      display: grid;
      grid-template-columns: max-content 1fr;
    }
  }

  .submit-section {
    margin-top: 58px;
    padding-top: 32px;
    border-top: 1px solid $borderGray;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .tnc-container {
    display: inline-flex;
    width: fit-content;
    align-items: center;
    color: #343434;

    .checkbox-placeholder {
      height: 18px;
      width: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 3px;
      border: 1px solid #a19f9f;
      margin-right: 5px;
      color: $primaryColor;
      font-size: 0;
      cursor: pointer;
    }

    .tnc-checkbox:checked + .checkbox-placeholder {
      background: $primaryColor;
      color: white;
      font-size: 0.9rem;
    }
  }

  .submit-button {
    height: 40px;
    width: 100%;
    outline:none;
    background: #F1F1F1;
    border: 1px solid #B8B7B7;
    color: #535353;
    cursor: pointer;

    &:hover {
      color: $darkColor;
    }
  }
}
</style>