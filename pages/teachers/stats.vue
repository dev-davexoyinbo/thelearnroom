<template>
  <div id="teachers-stats-page">
    <h1 class="h1 heading">Detailed Stats</h1>
    <div class="stats-info">
      <div class="content">
        Lorem ipsum dolor sit amet, consectetur adi pisicing elit, sed do
        eiusmod tempor incididunt ut l et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco
      </div>
    </div>

    <div class="stats-section">
      <h3 class="h3 heading">Total Summary</h3>
      <div class="summary-value-group">
        <div class="summary-value-item">
          <div class="value">99</div>
          <span class="highlight">Learners Taught</span>
        </div>
        <div class="summary-value-item">
          <div class="value">9</div>
          <span class="highlight">Hours Taught</span>
        </div>
        <div class="summary-value-item">
          <div class="value">$999</div>
          <span class="highlight">Longtime Earning</span>
        </div>
      </div>
    </div>

    <div class="stats-section">
      <h3 class="h3 heading">Monthly Summary</h3>
      <div class="table-container">
        <table class="table">
          <thead class="thead">
            <tr class="trow">
              <th class="th">Months</th>
              <th class="th">Earnings</th>
              <th class="th">Learners</th>
              <th class="th">Hours</th>
            </tr>
          </thead>
          <tbody class="tbody">
            <tr class="trow">
              <td class="td">February 2021</td>
              <td class="td">$999</td>
              <td class="td">99</td>
              <td class="td">9.00</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="stats-section">
      <h3 class="h3 heading">Yearly Summary</h3>
      <div class="table-container">
        <table class="table">
          <thead class="thead">
            <tr class="trow">
              <th class="th">Year</th>
              <th class="th">Earnings</th>
              <th class="th">Hours</th>
            </tr>
          </thead>
          <tbody class="tbody">
            <tr class="trow">
              <td class="td">February 2021</td>
              <td class="td">$999</td>
              <td class="td">9.00</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="stats-section">
      <h3 class="h3 heading">Classes BreakDown - Last Month</h3>
      <div class="table-container">
        <table class="table">
          <thead class="thead">
            <tr class="trow">
              <th class="th">Class</th>
              <th class="th">Type</th>
              <th class="th">Section</th>
              <th class="th">Learners</th>
              <th class="th">Hours</th>
              <th class="th">Earnings</th>
              <th class="th">Re-enroll</th>
              <th class="th">Rating</th>
              <th class="th">Reviews</th>
              <th class="th">Saves</th>
            </tr>
          </thead>
          <tbody class="tbody">
            <tr class="trow" v-for="i in 7" :key="i">
              <td class="td">My Class {{ i }}</td>
              <td class="td">1 Time</td>
              <td class="td">2</td>
              <td class="td">65</td>
              <td class="td">9</td>
              <td class="td">$54</td>
              <td class="td">85%</td>
              <td class="td">5.6</td>
              <td class="td">15</td>
              <td class="td">9</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "teachers",
};
</script>

<style lang="scss">
@import "~assets/styles/variables";
#teachers-stats-page {
  padding: 24px var(--body-padding);
  .stats-info {
    margin: 18px 0;
    padding: 16px;
    background: #f4fbc6;
    border-top: 1px solid $borderGray;
    border-bottom: 1px solid $borderGray;
    .content {
      max-width: 600px;
      text-align: center;
      color: black;
      font-size: 0.85rem;
      margin-right: auto;
      margin-left: auto;
    }
  }

  .stats-section {
    margin-bottom: 48px;
    &:last-child {
      margin-bottom: 0;
    }
    .heading {
      margin-bottom: 12px;
    }
  }

  .summary-value-group {
    display: flex;
    align-items: center;
    .summary-value-item {
      text-align: center;
      padding: 4px 16px;

      border-right: 1px solid $borderGray;

      &:last-child {
        border-right: none;
      }

      .value {
        font-size: 1.2rem;
      }
      .highlight {
        font-size: 0.85rem;
      }
    }
  }

  .table-container {
    overflow-x: auto;
  }

  .table {
    .th,
    .td {
      white-space: nowrap;
    }
  }
}
</style>