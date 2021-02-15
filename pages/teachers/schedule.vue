<template>
  <div id="teachers-schedule-page">
    <div class="display-options-container">
      <div class="display-option">
        <i class="icon fas fa-check-circle"></i>
        <span>Show Flexible Schedule Classes</span>
      </div>
      <div class="display-option">
        <i class="icon fas fa-check-circle"></i>
        <span>Show Classes with no Enroll</span>
      </div>
    </div>

    <div class="schedule-header">
      <div class="left">
        <div class="today-box">Today</div>
        <div>

        <i class="icon right fas fa-angle-left"></i>
        </div>
        <div>

        <i class="icon right fas fa-angle-right"></i>
        </div>
        <div class="date">January 21 Onward</div>
      </div>
      <div class="right">
        <div class="right-left">
          <div class="button-group">
            <button class="button-item active">Agender</button>
            <button class="button-item">Week</button>
            <button class="button-item">Month</button>
          </div>
          <div class="divider"></div>
          <div class="right-right">
            <button class="subscribe-button">Subscribe</button>
          </div>
        </div>
      </div>
    </div>

    <p class="no-meeting-text">You have no meeting on this schedule</p>
  </div>
</template>

<script>
export default {
  layout: "teachers",
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#teachers-schedule-page {
  padding: 24px var(--body-padding);
  .display-options-container {
    max-width: 600px;
    display: flex;
    cursor: pointer;
    color: black;
    font-size: 1.1rem;
    margin-bottom: 32px;
    flex-direction: column;

    @media only screen and (min-width: 768px) {
      justify-content: space-between;
      align-items: center;
      flex-direction: row;
    }
    .display-option {
      margin-bottom: 8px;
      @media only screen and (min-width: 768px) {
        margin-bottom: 0;
      }
      &:first-child {
        margin-bottom: 0;
        @media only screen and (min-width: 768px) {
          margin-right: 16px;
        }
      }

      .icon {
        color: $darkColorAlt;
      }
    }
  }

  .no-meeting-text {
    font-size: 0.9rem;
  }

  .schedule-header {
    display: flex;
    color: black;
    margin-bottom: 24px;
    flex-direction: column;

    @media only screen and (min-width: 768px) {
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
    }

    .left {
      display: flex;
      align-items: center;
      order: 2;

      @media only screen and (min-width: 768px){
        order: 1;
      }
      & > * {
        margin-right: 22px;
        &:last-child {
          margin-right: 0;
        }
      }
      .date {
        font-weight: 300;
        font-size: 1.2rem;
      }

      .icon {
        font-size: 1.3rem;
        cursor: pointer;
      }

      .today-box {
        height: 35px;
        padding-right: 16px;
        padding-left: 16px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        border: 1px solid $borderGray;
        box-shadow: -0.5px 2px rgba($borderGray, 0.8);
      }
    }

    .right {
      order: 1;
      margin-bottom: 16px;
       @media only screen and (min-width: 768px) {
         margin-bottom: 0;
       }
      .right-left {
        display: flex;
        align-items: center;
        flex-wrap: wrap;

        & > * {
          margin-bottom: 8px;
        }
        @media only screen and (min-width: 350px) {
           display: grid;
           grid-template-columns: repeat(3, max-content);
           gap: 12px;
           & > * {
          margin-bottom: 0px;
        }
         }

        .divider {
          width: 1px;
          height: 100%;
          background: $borderGray;
          display: none;
           @media only screen and (min-width: 350px) {
             display: flex;
           }
        }
      }

      .button-group {
        height: 35px;
        border: 1px solid lighten($darkColorAlt, 20%);
        border-radius: 5px;
        overflow: hidden;
        display: flex;

        .button-item {
          height: 100%;
          outline: none;
          border: none;
          background: white;
          color: $darkColorAlt;
          flex: 1;
          border-right: 1px solid lighten($darkColorAlt, 20%);
          padding: 0 12px;
          cursor: pointer;
          &:active {
            outline: none;
          }

          &:last-child {
            border-right: none;
          }

          &.active {
            color: white;
            background: $darkColorAlt;
          }
        }
      }

      .right-right {
        .subscribe-button {
          height: 35px;
          outline: none;
          border: none;
          background: white;
          color: $darkColorAlt;
          border: 1px solid lighten($darkColorAlt, 20%);
          border-radius: 5px;
          padding: 0 12px;
          cursor: pointer;
          &:active {
            outline: none;
          }
        }
      }
    }
  }
}
</style>