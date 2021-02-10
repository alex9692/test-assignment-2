<template>
  <section class="section">
    <div class="container">
      <div class="level">
        <div class="level-item has-text-centered">
          <p class="has-text-weight-medium is-size-4">Answered Questions:</p>
          <span class="answer-count has-text-white">2</span>
        </div>
      </div>
      <div class="level">
        <div class="level-item has-text-centered">
          <p class="has-text-weight-bold is-size-6">Time left :</p>
          <p class="has-text-weight-normal is-size-6">58 min and 52 sec</p>
        </div>
      </div>
      <div class="level">
        <div class="level-item has-text-centered">
          <button class="button button-custom button-size is-size-4">
            Question Pallete
          </button>
        </div>
      </div>
      <div class="card">
        <div class="card-content card-item-container">
          <template v-for="(item, index) in count">
            <div
              :key="index"
              :class="[
                item === 2 ? 'not-answered-item' : '',
                item === 4 ? 'correct-item' : '',
                'card-item',
              ]"
            >
              <p class="card-item-text">
                <span v-if="item === 2" class="tick-icon">&#10003;</span>
                {{ item }}
              </p>
            </div>
          </template>
        </div>
      </div>
      <p class="subtitle mt-5">Legend:</p>
      <div class="columns">
        <div class="column icon-container">
          <div class="answered-icon"></div>
          <span>Answered</span>
        </div>
        <div class="column icon-container">
          <div class="not-answered-icon"></div>
          <span>Not Answered</span>
        </div>
      </div>
      <div class="columns">
        <div class="column icon-container">
          <div class="not-answered-plus-review-icon"></div>
          <span>Not Answered & Marked for Review</span>
        </div>
        <div class="column icon-container">
          <div class="answered-plus-review-icon">
            <span class="tick-icon">&#10003;</span>
          </div>
          <span>Answered & Marked for UnReview</span>
        </div>
      </div>
      <div class="field is-grouped center-buttons">
        <p class="control">
          <button class="button is-warning">
            <span class="icon is-small">
              <i class="fas fa-book"></i>
            </span>
            <span>Question Paper</span>
          </button>
        </p>
        <p class="control">
          <button class="button is-danger">
            <span class="icon is-small"><i class="fas fa-times"></i></span>
            <span>Exit</span>
          </button>
        </p>
      </div>
      <div class="center-buttons">
        <button class="button is-success">
          <span class="icon is-small"><i class="fas fa-check-double"></i></span>
          <span>Submit</span>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      count: 20,
    };
  },
};
</script>

<style scoped>
.answer-count {
  background-color: #5ac75a;
  border-radius: 20px;
  padding: 0 0.75rem;
  font-size: 1rem;
  margin-left: 0.5rem;
}
.button-size {
  width: 90%;
  background-color: #4444a0 !important;
  color: white;
}
.section {
  position: relative;
}
.button-custom {
  position: absolute;
  margin-top: 3.5rem;
  z-index: 10;
  padding: 1.7rem 0;
}

.card-item-container {
  display: flex;
  flex-wrap: wrap;
  padding: 3rem;
  padding-bottom: 1rem;
  margin: 0 3rem;
  margin-top: 6rem;
  background: #f3f2f2;
}

.card-item {
  width: 1.75rem;
  margin: 0 0.75rem;
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  background-color: #e9e3e3;
  border: 1px solid #838383;
  border-radius: 5px;
  cursor: pointer;
}

.card-item-text {
  position: relative;
  width: 100%;
  text-align: center;
}
.card-item-text .tick-icon {
  position: absolute;
  bottom: 10px;
  left: 5px;
  color: #5ac75a;
  font-size: 1.2rem;
  font-weight: bold;
}
.not-answered-item {
  border-radius: 50%;
  background-color: rgb(187, 85, 187);
  border-color: black;
  color: white;
}

.correct-item {
  position: relative;
  background-color: #000;
  -webkit-clip-path: polygon(
    25% 0%,
    75% 0%,
    100% 38%,
    100% 100%,
    0 100%,
    0 38%
  );
  clip-path: polygon(25% 0%, 75% 0%, 100% 38%, 100% 100%, 0 100%, 0 38%);
}
.correct-item .card-item-text {
  position: relative;
  background-color: #5ac75a;
  color: white;
  -webkit-clip-path: polygon(
    25% 0%,
    75% 0%,
    100% 38%,
    100% 100%,
    0 100%,
    0 38%
  );
  clip-path: polygon(25% 0%, 75% 0%, 100% 38%, 100% 100%, 0 100%, 0 38%);
}
.icon-container {
  display: flex;
}
.answered-icon {
  width: 20px;
  height: 20px;
  margin-right: 1rem;
  background-color: #5ac75a;
  -webkit-clip-path: polygon(
    25% 0%,
    75% 0%,
    100% 38%,
    100% 100%,
    0 100%,
    0 38%
  );
  clip-path: polygon(25% 0%, 75% 0%, 100% 38%, 100% 100%, 0 100%, 0 38%);
}
.not-answered-icon {
  width: 20px;
  height: 20px;
  margin-right: 1rem;
  background-color: #e9e3e3;
  border: 1px solid #838383;
  border-radius: 5px;
}

.not-answered-plus-review-icon,
.answered-plus-review-icon {
  width: 20px;
  height: 20px;
  margin-right: 1rem;
  border: 1px solid black;
  border-radius: 50%;
  background-color: rgb(187, 85, 187);
  position: relative;
}

.tick-icon {
  position: absolute;
  bottom: 5px;
  left: 7px;
  color: #5ac75a;
  font-size: 1.2rem;
  font-weight: bold;
}

.center-buttons {
  display: flex;
  justify-content: center;
}
</style>
