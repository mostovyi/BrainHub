<template>
  <div>
    <div>
      <button @click="getNewNumbersArray( repeats )">Result is: {{ answer }}</button>
    </div>
    <div>
      <div class="numbers-block" v-for="(element, i) in array" :key=" 'A'+ i">{{ element }} </div>
    </div>
  </div>
</template>

<script>
// For now this function works, but input parameters are hardcoded
export default {
  name: "EasyOneTwo",
  data() {
    return {
      array: [],
      answer: 0
    }
  },
  // Input parameters
  props: ["repeats"],
  // Digits generation function
  methods: {
    getNewNumbersArray: function(repeats) {
      console.log("EasyOneTwo")
      let temporalArrayWithNumbers = [];
      let interimAnswer = 0;
      let currentValue = 0;
      for(let i = 0; i < repeats; i++){

        switch (interimAnswer) {
            // If current step is equals to Zero, we make following
          case 0: {
            currentValue = this.getRandomIntInclusive(1, 2);
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
            // If current step is equals to One, we make following
          case 1: {
            let list1 = [1,-1, 2];
            currentValue = this.getRandomIntInclusive(0, 2);
            currentValue = list1[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
            // If current step is equals to Two, we make following
          case 2: {
            let list2 = [-2,-1, 1, 2];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list2[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
            // If current step is equals to Three, we make following
          case 3: {
            let list3 = [-2,-1, 1];
            currentValue = this.getRandomIntInclusive(0, 2);
            currentValue = list3[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
            // If current step is equals to Four, we make following
          case 4: {
            let list4 = [-2,-1];
            currentValue = this.getRandomIntInclusive(0, 1);
            currentValue = list4[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
        }
      }
      this.array = temporalArrayWithNumbers;
      this.answer = interimAnswer;
    },
    // Generates random values
    getRandomIntInclusive: function(min, max) {
      return Math.floor(Math.random() * (max - min + 1)) + min; //Максимум и минимум включаются
    }
  }
}
</script>

<style scoped>
  button {
    background-color: red; /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
  }
</style>