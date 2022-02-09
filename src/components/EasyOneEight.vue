<template>
  <div>
    <div>
      <button @click="rangeOneTwo( repeats )">Result is: {{ answer }}</button>
    </div>
    <div>
      <div v-for="(element, i) in array" :key=" 'A'+ i">{{ element }} </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EasyOneEight",
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
    rangeOneTwo: function(repeats) {
      let temporalArrayWithNumbers = [];
      let interimAnswer = 0;
      let currentValue = 0;
      for(let i = 0; i < repeats; i++){

        switch (interimAnswer) {

          case 0: {
            currentValue = this.getRandomIntInclusive(1, 8);
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 1: {
            let list1 = [1, 2, 3, 5, 6, 7, 8, -1];
            currentValue = this.getRandomIntInclusive(0, 7);
            currentValue = list1[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 2: {
            let list2 = [1, 2, 5, 6, 7, -1, -2];
            currentValue = this.getRandomIntInclusive(0, 6);
            currentValue = list2[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 3: {
            let list3 = [1, 5, 6, -3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list3[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 4: {
            let list4 = [5, -4, -3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 4);
            currentValue = list4[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 5: {
            let list5 = [-5, 1, 2, 3, 4];
            currentValue = this.getRandomIntInclusive(0, 4);
            currentValue = list5[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 6: {
            let list6 = [-6, -5, -1, 1, 2, 3];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list6[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 7: {
            let list7 = [-7, -6, -5, -2, -1, 1, 2];
            currentValue = this.getRandomIntInclusive(0, 6);
            currentValue = list7[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 8: {
            let list8 = [-8, -7, -6, -5, -3, -2, -1, 1];
            currentValue = this.getRandomIntInclusive(0, 7);
            currentValue = list8[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 9: {
            let list9 = [-8, -7, -6, -5, -4, -3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 7);
            currentValue = list9[currentValue];
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

</style>