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
  name: "EasyOneSix",
  data: function () {
    return {
      array: [],
      answer: 0
    }
  },
  // Input parameters
  props: {
    repeats : Number
  },
  // Digits generation function
  methods: {
    rangeOneTwo : function (repeats) {
      let help = [];
      let helpAnswer = 0;
      let currentValue = 0;
      for(let i = 0; i < repeats; i++){

        switch (helpAnswer) {

          case 0: {
            currentValue = this.getRandomIntInclusive(1, 6);
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 1: {
            let list1 = [-1, 1, 2, 3, 5, 6];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list1[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 2: {
            let list2 = [-2, -1, 1, 2, 5, 6];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list2[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 3: {
            let list3 = [-3, -2, -1, 1, 5, 6];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list3[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 4: {
            let list4 = [-4, -3, -2, -1, 5];
            currentValue = this.getRandomIntInclusive(0, 4);
            currentValue = list4[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 5: {
            let list5 = [-5, 1, 2, 3, 4];
            currentValue = this.getRandomIntInclusive(0, 4);
            currentValue = list5[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 6: {
            let list6 = [-6, -5, -1, 1, 2, 3];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list6[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 7: {
            let list7 = [-6, -5, -2, -1, 1, 2];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list7[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 8: {
            let list8 = [-6, -5, -3, -2, -1, 1];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list8[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
          case 9: {
            let list9 = [-6, -5, -4, -3, -2, -1];
            currentValue = this.getRandomIntInclusive(0, 5);
            currentValue = list9[currentValue];
            help.push(currentValue);
            helpAnswer += currentValue;
            break;
          }
        }
      }
      this.array = help;
      this.answer = helpAnswer;
    },
    // Generates random values
    getRandomIntInclusive : function (min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min + 1)) + min; //Максимум и минимум включаются
    }
  }
}
</script>

<style scoped>

</style>