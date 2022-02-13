<template>
  <div id="algorithms-block">
    <!-- Choosing block Easy, list of all possible possibilities -->
    <b-dropdown class="mx-1" variant="outline-danger" right text="Просто">
      <b-dropdown-item variant="primary" v-for="tab in tabsEasy"
                       v-bind:key="tab"
                       v-bind:class="['tab-button', { active: currentTab === tab }]"
                       v-on:click="currentTab = tab"
      >{{ tab }}</b-dropdown-item>
    </b-dropdown>
    <!-- Choosing block Brother, list of all possible possibilities -->
    <b-dropdown class="mx-1" variant="outline-success" right text="Брат">
      <b-dropdown-item variant="primary" v-for="tab in tabsBrother"
                       v-bind:key="tab"
                       v-bind:class="['tab-button', { active: currentTab === tab }]"
                       v-on:click="currentTab = tab"
      >{{ tab }}</b-dropdown-item>
    </b-dropdown>
    <!-- Chosen level and difficulty -->
    <p>Выбранный режим: {{ currentTab }}</p>
    <!-- Input fields for repeats amount and speed -->
    <b-row>
      <b-col>
        <b-form-input v-model="repeats" type="number" debounce="500"></b-form-input>
      </b-col>
      <b-col>
        <b-form-input v-model="speed" type="number" step="0.1" debounce="500"></b-form-input>
      </b-col>
      <div class="w-100"></div>
      <b-col>
        <div class="mt-2">Количество повторений: "{{ repeats }}"</div>
      </b-col>
      <b-col>
        <div class="mt-2">Скорость: "{{ speed }}" сек</div>
      </b-col>
    </b-row>
    <b-button variant="success" v-on:click="startTimer">Generate values</b-button>
    <div class="generated-value">
      <p> {{currentValue}} </p>
    </div>
    <!-- Progress -->
    <b-progress :value="sequenceNumber" :max="numberArray.length" show-progress animated></b-progress>
  </div>
</template>

<script>
export default {
  name: "AlgorithmsUI",
  data: function () {
    return {
      currentTab: "EasyOneTwo",
      // Have to change in on our generated array
      numberArray: [1,2,3,4,5,6,7,8,9,10],
      // Current value, needed for progress block
      sequenceNumber: 0,
      // Value, that will be displayed on Users screen
      currentValue: null,
      // Repeats amount from input form
      repeats: 0,
      // Speed between digits displaying
      speed: 0,
      // All possibilities for each block. Have to be changed later
      tabsEasy: ["EasyOneTwo", "EasyOneThree", "EasyOneFour", "EasyOneFive", "EasyOneSix", "EasyOneSeven", "EasyOneEight", "EasyOneNine"],
      tabsBrother: ["BrotherOne", "BrotherTwo", "BrotherThree", "BrotherFour"]
    }
  },
  methods: {
    // Initializing this.numberArray TODO
    getNewNumbersArray: function() {},

    // Starting our timer, has to update this.currentValue each this.speed * 1000 milliseconds
    startTimer: function () {
      // Needed for setting on 0, if we are clicking one more time on Generate Button without page update
      this.sequenceNumber = 0;
      // initialize all calls right away
      this.numberArray.forEach(() => {
        setTimeout(() => {
          this.currentValue = this.numberArray[this.sequenceNumber];
          ++this.sequenceNumber;
          console.log(this.sequenceNumber + " " + this.currentValue);
        }, this.speed * 1000);
      });
    }
  }
}
</script>

<style scoped>

  #algorithms-block {
    margin: auto;
    max-width: 80%;
    max-height: 80%;
  }

</style>