<template>
  <div>
    <div>
      <button @click="getNewNumbersArray( repeats )">Result is: {{ answer }}</button>
    </div>
    <div>
      <div v-for="(element, i) in array" :key=" 'A'+ i">{{ element }} </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EasyOneThree",
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
      console.log("EasyOneThree")
      let temporalArrayWithNumbers = [];
      let interimAnswer = 0;
      let currentValue = 0;
      for(let i = 0; i < repeats; i++){

        switch (interimAnswer) {

          case 0: {
            currentValue = this.getRandomIntInclusive(1, 3);
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 1: {
            let list1 = [1, 2, 3, -1];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list1[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 2: {
            let list2 = [-2, -1, 1, 2];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list2[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 3: {
            let list3 = [-3, -2, -1, 1];
            currentValue = this.getRandomIntInclusive(0, 3);
            currentValue = list3[currentValue];
            temporalArrayWithNumbers.push(currentValue);
            interimAnswer += currentValue;
            break;
          }
          case 4: {
            let list4 = [-3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 2);
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

</style>