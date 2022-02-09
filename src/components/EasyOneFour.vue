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
  name: "EasyOneFour",
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
      let help = [];
      let temporalArrayWithNumbers = 0;
      let interimAnswer = 0;
      for(let i = 0; i < repeats; i++){

        switch (interimAnswer) {

          case 0: {
            interimAnswer = this.getRandomIntInclusive(1, 4);
            help.push(interimAnswer);
            temporalArrayWithNumbers += interimAnswer;
            break;
          }
          case 1: {
            let list1 = [-1, 1, 2, 3];
            interimAnswer = this.getRandomIntInclusive(0, 3);
            interimAnswer = list1[interimAnswer];
            help.push(interimAnswer);
            temporalArrayWithNumbers += interimAnswer;
            break;
          }
          case 2: {
            let list2 = [-2, -1, 1, 2];
            interimAnswer = this.getRandomIntInclusive(0, 3);
            interimAnswer = list2[interimAnswer];
            help.push(interimAnswer);
            temporalArrayWithNumbers += interimAnswer;
            break;
          }
          case 3: {
            let list3 = [-3, -2, -1, 1];
            interimAnswer = this.getRandomIntInclusive(0, 3);
            interimAnswer = list3[interimAnswer];
            help.push(interimAnswer);
            temporalArrayWithNumbers += interimAnswer;
            break;
          }
          case 4: {
            let list4 = [-4, -3, -2, -1];
            interimAnswer = this.getRandomIntInclusive(0, 3);
            interimAnswer = list4[interimAnswer];
            help.push(interimAnswer);
            temporalArrayWithNumbers += interimAnswer;
            break;
          }
        }
      }
      this.array = help;
      this.answer = temporalArrayWithNumbers;
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