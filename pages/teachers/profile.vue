<template>
  <div id="teachers-profile-page">
    <div class="header-section">
      <h1 class="h1 heading">Public teacher profile</h1>
      <div class="highlight">Save Changes <a href="#">Check here</a></div>
    </div>

    <div class="profile-content">
      <div class="profile-header">
        <div class="profile-photo-container">
          <h3 class="h3 heading">Profile Photo</h3>
          <img
            src="/images/profile-placeholder.png"
            class="profile-photo"
            alt=""
          />
          <a href="#">Select photo</a>
        </div>
        <div class="profile-details">
          <h3 class="h3 heading">
            Your Profile ( <a href="#">Check Here</a> )
          </h3>
          <div
            class="profile-progress-bar"
            :style="{ '--progress-factor': 0.7 }"
          ></div>
          <ul class="ul-list">
            <li>Lorem ipsum dolor sit amet</li>
            <li>Lorem ipsum dolor</li>
            <li>Lorem ipsum dolor sit amet</li>
            <li>Lorem ipsum dolor</li>
            <li>Lorem ipsum dolor sit amet</li>
            <li>Lorem ipsum dolor</li>
          </ul>
        </div>
      </div>

      <form action="" class="form">
        <div class="form-group">
          <label for="">Name: </label>
          <input type="text" class="form-control" />
        </div>
        <div class="form-group">
          <label for="">Title: </label>
          <input type="text" class="form-control" />
        </div>
        <div class="form-group with-text-area">
          <label for="">About me: </label>
          <textarea type="text" class="form-control"> </textarea>
        </div>
      </form>

      <div class="record-video-container">
        <span>Intro Video</span>
        <div>
          <generic-button :noBorder="true" :primary="true">
            Record Your Video</generic-button
          >
        </div>
      </div>

      <ul class="ul-list">
        <li>Lorem ipsum dolor sit amet</li>
        <li>Lorem ipsum dolor sit amet <a href="#">learn more</a></li>
        <li>Lorem ipsum dolor sit amet</li>
      </ul>

      <form class="form profile-url-form">
        <div class="form-group">
          <label for="">Profile URL</label>
          <div>
            <input
              type="text"
              class="form-control muted"
              value="http://"
              readonly
            />
            <a href="#">Change URL</a>
          </div>
        </div>
      </form>

      <form action="" class="form profile-settings-form">
        <h3 class="h3 heading">Profile Settings</h3>

        <div class="form-group">
          <label for="">Phone</label>
          <input type="text" class="form-control sm" />
        </div>
        <div class="form-group">
          <label for="">Teacher Identity Verification</label>
          <div>
            <generic-button :noBorder="true" :primary="true"
              >Verify</generic-button
            >
          </div>
        </div>
        <div class="form-group">
          <label for="">Paypal Email</label>
          <input type="text" class="form-control" />
        </div>
        <div class="form-group">
          <label for="">Location</label>

          <input type="text" class="form-control md" />
        </div>
        <div class="form-group align-start">
          <label for="">Primary Email</label>
          <div class="tlr--display-flex tlr--align-items-center">
            <input type="text" class="form-control md" />
            <a href="#">Resend Confirmation</a>
          </div>
        </div>

        <div class="form-group">
          <label for="">Email Settings</label>
          <a href="#">Email you receive</a>
        </div>

        <div class="form-group">
          <label for="">Password</label>
          <a href="#">Change your password</a>
        </div>

        <div class="form-group">
          <label for="">Payment Method</label>
          <div class="">
            <p><a href="#">Payment methods</a></p>
            <p>
              Do you have multiple The LearnRoom account?
              <a href="#"> Manage Account</a>
            </p>
          </div>
        </div>

        <div class="form-group align-start">
          <label for="">Facebook</label>
          <div class="">
            <p>Link your facebook account to log in easily</p>
            <div class="sized-box-height" style="--height: 4px"></div>
            <p>
              <generic-button
                :noBorder="true"
                :primary="true"
                :sizeFactor="1.2"
                :fontSizeFactor="0.8"
                >Connect with facebook</generic-button
              >
            </p>
          </div>
        </div>
      </form>

      <div class="logout-save-footer">
        <div class="logout-save-container">
          <generic-button
            :bgLight="true"
            :sizeFactor="1.2"
            :fontSizeFactor="0.8"
            >Logout</generic-button
          >
          <generic-button
            :noBorder="true"
            :primary="true"
            :sizeFactor="1.2"
            :fontSizeFactor="0.8"
            >Save</generic-button
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GenericButton from "~/components/buttons/GenericButton.vue";
export default {
  components: { GenericButton },
  layout: "teachers",
};
</script>

<style lang="scss">
@import "~assets/styles/variables";

#teachers-profile-page {
  padding: 24px var(--body-padding);
  .ul-list {
    margin-top: 12px;
    line-height: 20px;
  }
  a {
    color: $primaryColor;
    text-decoration: none;
  }
  .header-section {
    margin-bottom: 24px;
    color: black;
    .heading {
      margin-bottom: 2px;
    }
    .highlight {
      font-size: 0.9rem;
    }
  }

  .profile-content {
    max-width: 600px;
    margin-right: auto;
    margin-left: auto;
    .profile-header {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
      margin-bottom: 16px;

      @media only screen and (min-width: 768px) {
        grid-template-columns: 1fr max-content;
      }
      .profile-photo-container {
        padding: 0 16px;
        display: flex;
        flex-direction: column;
        align-items: center;
        font-size: 0.9rem;
        @media only screen and (min-width: 768px) {
          order: 2;
        }
        .profile-photo {
          width: 110px;
          height: 110px;
          margin-bottom: 16px;
          margin-top: 12px;
          object-fit: cover;
        }
      }
    }

    .profile-details {
      font-size: 0.9rem;

      .profile-progress-bar {
        --height: 20px;
        --progress-factor: 1;
        height: var(--height);
        border-radius: calc(var(--height) / 2);
        border: 1px solid $borderGray;
        margin-top: 8px;
        position: relative;
        &::after {
          content: "";
          background: $primaryColor;
          height: 100%;
          width: calc(100% * var(--progress-factor));
          top: 0;
          left: 0;
          position: absolute;
          border-radius: calc(var(--height) / 2);
        }
      }
    }

    .form {
      color: black;
      margin-top: 32px;
      font-size: 0.9rem;
      .form-group {
        display: grid;
        grid-template-columns: 12ch 1fr;
        align-items: center;
        gap: 8px;

        &.align-start {
          align-items: start;
        }

        &.with-text-area label {
          align-self: start;
        }
      }

      input.form-control {
        height: 30px;
        margin-bottom: 0;
      }
    }

    .record-video-container {
      display: flex;
      color: black;
      margin-bottom: 16px;
      & > *:first-child {
        padding-right: 32px;
        display: inline-flex;
        align-items: center;
      }
    }

    .profile-url-form {
      .form-group {
        align-items: start;
        .form-control {
          margin-bottom: 2px;
        }
        a {
          font-size: 0.75rem;
        }
        label {
          margin-top: 5px;
        }
      }
    }

    .profile-settings-form {
      .heading {
        margin-bottom: 16px;
      }

      .form-group {
        grid-template-columns: 14ch 1fr;
      }
    }

	.logout-save-footer {
		margin-top: 24px;
		padding-top: 24px;
		border-top: 1px solid $borderGray;
		.logout-save-container {
			display: grid;
			grid-template-columns: max-content max-content;
			width: fit-content;
			margin-left: auto;
			margin-right: auto;
			gap: 12px;
		}
	}
  }
}
</style>